# Архитектурное решение по трейсингу

## Tracing
> Напишите и выделите на схеме системы, которые следует покрыть трейсингом.

Сломаться заказ может как на этапе получения запроса от клиента по API, так и при попытке сохранения
его в БД.

Внедрять trace нужно во всех сервисах, чтобы понимать всю цепочку вызовов, на каком этапе обрывается 
процесс или наоборот, где можно подумать над моментами оптимизации. 

## Мотивация
- распределенная трассировка в микросервисной архитектуре необходима, для понимания всей цепочки вызовов
- проблема пользователей "медленное оформление заказа"
- теряются заказы, что сказывается на прибыли компании

## Компромиссы
Наличие распределенной трассировки не имеет смысла в рамках MVP решений, когда задействовано пару сервисов,
в таком случае трудозатраты на разворачивание необходимой инфраструктуры будут необоснованными.

## Security
Должна существовать в системе ролевая модель, которая определяется в application gateway, а дальшнейшие
в цепочке вызова сервисы работают с JWT токеном, в котором указааны необходимые roles/permissions и др. информация


