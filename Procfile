server: /usr/local/bin/gunicorn -b 0.0.0.0:5000 --name redash -w${REDASH_WEB_WORKERS:-4} redash.wsgi:app
scheduler: /usr/local/bin/celery worker --app=redash.worker --beat -c$WORKERS_COUNT -Q$QUEUES -linfo --maxtasksperchild=10 -Ofair
worker: /usr/local/bin/celery worker --app=redash.worker -c$WORKERS_COUNT -Q$QUEUES -linfo --maxtasksperchild=10 -Ofair