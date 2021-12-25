Кластер в cloud.google.

Приложение : nginx.

grafana и prometeus ставил с помощью helm.

создал ингрессы для nginx, grafana и прометея.

подцепил прометеус в графане, но нужных метрик не нашел.
список метрик прикладываю.

Поэтому создал  servic account для графана и полкллючил Google Cloud Monitoring
там нужные метрики нашлись (backend request count сгрупированные по metric.label.responce_code_class).

создал alert, создал канал в телеграмм 
в качестве нагрузки , скрипт на баше с двух машин:

url="http://35.190.0.139/tt"
while true
do content=$(curl "$url)$(query)")
  echo $content
done  

аллерты срабатывают.



nginx
http://35.190.0.139/

grafana
http://34.117.202.50/

promethus
http://34.149.156.193/

скриншот телеграм, прилагаю
яыки, пароли в письме

