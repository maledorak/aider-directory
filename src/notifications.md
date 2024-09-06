# Notifications

Sometimes code generation takes a long time and Aider don't support notification out of the box.
So we need to add it by ourselves 🚀

## iTerm2 (macOS)

We will use [iTerm2 Triggers](https://iterm2.com/documentation-triggers.html) to send notification.

First you have to turn on notifications for iTerm2 in MacOS settings `System Settings -> Notifications -> iTerm2 -> Allow Notifications`

Next, we need to add new trigger in iTerm2:

1. Open iTerm2
2. Go to `Settings -> Profiles -> Advanced -> Triggers`
3. Enable `Enabled in interactive apps` checkbox
4. Next, click on `Edit` button
5. Add new trigger (Click on `+` button on the left bottom)
6. In the `Regular expression` field, paste the following script (**copy it carefully without any whitespaces or newlines**):
    ```
    ^Tokens:\s\d+(?:\.\d+)?k?\ssent,\s\d+(?:\.\d+)?k?\sreceived\..*$
    ```
7. In the `Action` field, select `Post Notification`
8. In the `Parameters` field write the message like:
    ```
    Aider has finished
    ```
9. Enable `Enabled` checkbox
10. Click `Close` button
11. Notification should appear on every Aider code generation.

### Troubleshooting
- Check that you have enabled iTerm2 notifications in MacOS settings
- Check that you have enabled `Enabled in interactive apps` in iTerm2 settings
- Check that you have added trigger with correct regular expression, without any whitespaces or newlines
- Check that you have correct profile selected in iTerm2 settings
