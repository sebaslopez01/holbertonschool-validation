## Prerequisites
- GoHugo
- Go
- Git

## Lifecycle
Generate the website from the markdown and configuration files in the directory dist/
    make build
Cleanup the content of the directory dist/
    make clean
Create a new blog post whose filename and title come from the environment variables POST_TITLE and POST_NAME
    make post
View all make commands
    make help