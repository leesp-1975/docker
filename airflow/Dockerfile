FROM python:3.7
RUN pip3 install 'apache-airflow'
RUN pip3 install 'airflow-code-editor'
RUN mkdir -p /root/airflow/dags /root/airflow/plugins /root/airflow/logs
RUN apt-get update && apt-get install git
RUN airflow db init
RUN airflow users create \
 --username admin \
 --firstname SAMSUNG \
 --lastname DS \
 --role Admin \
 --password admin \
 --email sangpil.lee@bespinglobal.com

COPY ./airflow.cfg /root/airflow/airflow.cfg

CMD (airflow scheduler &) && airflow webserver
