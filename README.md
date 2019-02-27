# jammer

AutoSSH container for a jambox

## Setup

Generate a new jammer-specific ssh key for the jammer, you don't want
to use your own key for this do you?

	$ ssh-keygen -t rsa -f ~/.ssh/jammer_rsa -N ''

Create a `.env` file in this directory to describe the jambox host and account.

	JAMBOX_USER=<username>
	JAMBOX_HOST=<hostname>
	
Copy the above public key onto the jambox.

	source .env
	ssh-copy-id -i ~/.ssh/jammer_rsa $JAMBOX_USER@$JAMBOX_HOST
	
## Usage

	docker-compose up -d
	
Once running from you $JAMBOX_HOST you can ssh to your local machine
(the docker host).

	ssh -p $JAMBOX_PORT <username>@localhost



