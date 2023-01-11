## Prerequisites
- GoHugo
- Go
- Git

## Lifecycle
- make build - Generate the website from the markdown and configuration files in the directory dist/
- make clean - Cleanup the content of the directory dist/
- make post - Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
- make help - View all make commands