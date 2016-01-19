# slack-form
A Web Component that offers users a form to post directly to a slack channel.
It was made with the intention to provide an easy way to submit feedback and bug report.
Optionaly users can append browser details in the message.

Messages can include page title, URL and stringified browser details.


# Usage
```
			<slack-form
				webhook-url="{Webhook URL from `Incoming WebHooks` integration}"
				channel="#the_channel"
				current-page-title="[[currentAppletTitle]]"
				browser-info-text="something is broken, attach my browser details"
				on-message-sent="slackMessageSent"
				on-error="slackError"
			></slack-form>
```

The event handlers on-message-sent and on-error are optional. They could look like this:
```
slackMessageSent: function(e) { app.toastMsg('Thanks for your feedback, '+e.detail.username.split(' ')[0]+'!'); },
slackError: function(e) { app.errorMsg(e.detail.error); },
```


If you skip the attribute ```browser-info-text``` this feature will be disabled.
