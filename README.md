# GITLAB CI NOTIFICATION

### available notification
- telegram

### Telegram
```yaml
stages:
    - notification
success_notification:
    stage: notification
    script:
        - wget https://raw.githubusercontent.com/synergicsdigital/gitlab-ci-notif/main/telegram.sh
        - chmod +x telegram.sh
        - ./telegram.sh success $BOT_TOKEN $CHAT_ID
    when: on_success

failure_notification:
    stage: notification
    script:
        - wget https://raw.githubusercontent.com/synergicsdigital/gitlab-ci-notif/main/telegram.sh
        - chmod +x telegram.sh
        - ./telegram.sh failure $BOT_TOKEN $CHAT_ID
    when: on_failure
```
