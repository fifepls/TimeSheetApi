# TimeSheetApi
Konstantin Bezborodov timesheet rest api pet project
Используемые технологии: PostgreSQL, Maven, Spring(boot, web mvc, data, security)

Timesheet представляет собой небольшое Rest web api для менеджмента отработанных часов по датам для сотрудников.

Реализована авторизация с базы данных по имени и паролю.
У пользователя есть роли.
Роли основаны на правах.

Функционал роли руководитель: (mapping localhost:8080/Director/
Может добавлять новых сотрудников, (/addNewWorker с параметрами name, passowrd, role
Может добавлять сотрудникам отработанные часы (/addHoursToWorkker с параметрами name, date, hours)
Может получать отчет по отработанным часам по датам для определенного сотрудника (/makeReportForWorker с параметрами name, date, daysValue может быть day,week,month)
Может получать отчет по отработанным часам по датам для всех сотрудников (/makeReportForAll с параметрами начала date , и интервала который может быть day,week,month) 
Может удалять работника (/removeWorker с парамтрами name)

Функционал роли штатный работник: (mapping localhost:8080/Worker/

Может добавлять отработанные часы только за себя (/selfHoursAdd с параметрами date, и hours)
Может получать отчет только за себя (/selfReport с параметрами date, daysValue может быть day,week,month)


Функционал роли фрилансер(mapping localhost:8080/Freelance)
Может добавлять часы себе, только если от текущей даты прошло не более двух дней(/selfHoursAdd с параметрами date, hours)
Может получать отчет только за себя (/selfReport с параметрами date, daysValue может быть day,week,month).
