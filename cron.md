Для редатирования списка заданий cron, ввести команду

```
crontab -e
```

откроется редактор vim, и вводить задания в него

пример

```
# Edit this file to introduce tasks to be run by cron.
#
# Each task to run has to be defined through a single line
# indicating with different fields when the task will be run
# and what command to run for the task
#
# To define the time you can provide concrete values for
# minute (m), hour (h), day of month (dom), month (mon),
# and day of week (dow) or use '*' in these fields (for 'any').#
# Notice that tasks will be started based on the cron's system
# daemon's notion of time and timezones.
#
# Output of the crontab jobs (including errors) is sent through
# email to the user the crontab file belongs to (unless redirected).
#
# For example, you can run a backup of all your user accounts
# at 5 a.m every week with:
# 0 5 * * 1 tar -zcf /var/backups/home.tgz /home/
#
# For more information see the manual pages of crontab(5) and cron(8)
#
# m h  dom mon dow   command

* */1 * * * /etc/cron.hourly/build.sh
```

Команды имеют следующий формат

```
* * * * * {пользователь} выполняемая_команда
- - - - -
| | | | |
| | | | ----- День недели (0 - 7) (Воскресенье =0 или =7)
| | | ------- Месяц (1 - 12) (можно три буквы из названия месяца,
| | |                        регистр не имеет значения от jan до dec)
| | --------- День (1 - 31)
| ----------- Час (0 - 23)
------------- Минута (0 - 59)
```

### Готовые настройки cron 

Выполнение комманды раз в 2 часа

```
0 */2 * * * /cmd/
```
