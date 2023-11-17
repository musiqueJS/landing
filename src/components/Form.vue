<script lang="ts">
import base from '../airtable'
import toastr from 'toastr'

export default {
	data() {
		return {
			emailValue: '',
			isLoading: false
		}
	},

	methods: {
		validEmail(email: string) {
			const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
  			return emailRegex.test(email)
		},

		async sendToAirtable(email: string) {

			if(this.validEmail(email)) {

				try {
					this.isLoading = true

					let dateValue = Date.now()

					let record: any = [
					{
							"fields": {
								"Email": email,
								"Date": dateValue,
								"Status": "Not Sent"
							}
						}
					]

					await base('Waitlist').create(record)

					this.emailValue = ""

					toastr.success('Votre email a bien été envoyé')

				} catch(error) {
					// Catch l'error
					console.error('Erreur lors de l\'envoi', error)
					return;
					
				} finally {
					this.isLoading = false
				}
			} else {
				toastr.error('Adresse e-mail non valide');
			}
		}
	},

	name: 'Form',
}
</script>

<template>
	<div id="waitlist" class="form">
		<h2>Join Waitlist</h2>
		<p>Get notified when <span>Musique.js</span> is ready for you.</p>
		<form>
			<input v-model="emailValue" type="email" placeholder="Email" />
			<input @click="sendToAirtable(emailValue)" type="button" :value="isLoading ? 'Sending...' : 'Send'" :disabled="isLoading">
		</form>
	</div>
</template>

<style scoped>
	.form {
		width: 100%;
		height: 40vh;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.form > * {
		margin: 1rem;
	}

	.form > form {
		display: flex;
		flex-direction: column;
		width: 100%;
		gap: 1rem;
	}

	.form > form > * {
		margin: 0.5rem;
	}

	.form > form > input[type=email] {
		margin: 0 auto;
		width: 50%;
		font-size: 1.5rem;
		height: 3rem;
		border: 1px solid #cccccc30;
		border-radius: 0.5rem;
		padding: 0.5rem;
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	.form > form > input[type=button] {
		font-size: 1.5rem;
		margin: 0 auto;
		width: 20rem;
		height: 3rem;
		border: none;
		border-radius: 0.5rem;
		padding: 0.5rem;
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		color: #fff;
		cursor: pointer;
	}

	.form > form > input[type=button]:hover {
		background: white;
		transform: scale(1.1);
		transition: all 0.3s ease-in-out;
		color: #7000ff;
	}

	h2 {
		font-size: 2rem;
	}

	p {
		font-size: 1.5rem;
	}

	span {
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	@media screen and (max-width: 1024px) {
		.form {
			height: auto;
			margin: 8rem 0;
			text-align: center;
		}

		.form > form > input {
			width: 80%;
		}

		.form > form > button {
			width: 80%;
		}
	}
</style>