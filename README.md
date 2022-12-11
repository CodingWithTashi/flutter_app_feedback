# in_app_feedback
in_app_feedback is a simple feedback package that let user to provide feedback and raise issue from your application

## Features
Get your user feedback without user leaving the application.
* Create an issue in GitHub
* Get feedback via mail through SendGrid
* Add record in firebase [Future]   

## Demo
<img src="https://user-images.githubusercontent.com/25583737/206891217-9bec1f43-aa9b-46be-9ce0-ab4e9aba6aec.jpeg" width=250/>

## Prerequisite   
### Generate API Key
* GitHub secret token generate fom [here](https://github.com/settings/tokens?type=beta)   
  - Go to `Geenerate new Token`
  - Set `token name`, `expiration`
  - Select `Repository access` and `Permissions` eg. `read write issue`   
  
* SendGrid Key generate from SendGrid Email API from [here](https://app.sendgrid.com/guide/integrate)
  - Create` and verify SendGrid account
  - open [https://app.sendgrid.com/guide/integrate/langs/curl](https://app.sendgrid.com/guide/integrate/langs/curl)   
  - `Provide API Name` and click `Create Key`


## Getting started   

```dart
in_app_feedback: ^0.0.1

```

## Usage

```dart
FlutterFeedback.showFeedback(
                context: context,
                emailConfig: EmailConfig(
                  toMail: 'developer.kharag@gmail.com',
                  sendGridToken: 'send_grid_key',
                ),
                gitHubConfig: GitHubConfig(
                  accessToken: 'access_token',
                  githubUserName: 'github_user_name',
                  repositoryName: 'github_repo_name',
                ),
                feedbackCallback: (FeedbackData data) {
                  if (data.error == null) {
                    ScaffoldMessenger.of(context).showSnackBar(
                        const SnackBar(content: Text("Feedback Sent")));
                  } else {
                    ScaffoldMessenger.of(context)
                        .showSnackBar(SnackBar(content: Text(data.error!)));
                  }
                },
              );
```

## Additional information

Feel free to fork and send pull request

If you have any questions, feedback or ideas, feel free to [create an
issue](https://github.com/CodingWithTashi/in_app_feedback/issues/new). If you enjoy this
project, I'd appreciate your [🌟 on GitHub](https://github.com/CodingWithTashi/in_app_feedback/).

## You can also buy me a cup of coffee
<a href="https://www.buymeacoffee.com/codingwithtashi"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" width=200px></a>
