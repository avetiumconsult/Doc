System Architecture Diagram
===========================

This diagram shows the high-level architecture of ABAS..

.. mermaid::


   architecture-beta
    group frontend(cloud)[Frontend]
    group backend(cloud)[Backend API Layer]
    group redis_group(cloud)[Redis]
    group celery_group(cloud)[Celery Processing]
    group sources(cloud)[External Sources]
    group azure(cloud)[Azure Cloud]

    service web(internet)[Web Application] in frontend

    service api(server)[DRF API] in backend
    service auth(server)[Authentication] in backend
    service db(database)[PostgreSQL] in backend

    service broker(server)[Redis Broker] in redis_group

    service worker(server)[Celery Worker] in celery_group
    service beat(server)[Celery Beat] in celery_group

    service hodu(server)[HoduSoft] in sources
    service custom(server)[Other Sources] in sources

    service blob(disk)[Azure Blob Storage] in azure

    web:R --> L:api
    api:B --> T:auth
    api:B --> T:db
    api:R --> L:broker
    beat:R --> L:broker
    worker:L --> R:db
    broker:B --> T:worker
    worker:R --> L:hodu
    worker:R --> L:custom
    worker:B --> T:blob


**A. Frontend**:
The web application through which users manage backups, browse call records, and play archived recordings.

**B. Backend API Layer**:
DRF API, authentication handling, and PostgreSQL.

**C. Redis**:
The dedicated message broker used to queue asynchronous jobs.

**D. Celery Processing**:
Celery Worker executes queued backup and retrieval tasks; Celery Beat schedules recurring jobs.

**E. External Sources**:
HoduSoft and other supported systems that provide call-record data.

**F. Azure Cloud**:
Azure Blob Storage holds archived audio recordings and JSON backup records.


Go back
-------

Return to the :ref:`architecture-overview` section.
