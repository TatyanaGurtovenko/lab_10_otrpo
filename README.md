# lab_10_otrpo

Приложение-экспортер на Python
## Запуск

1. Клонируйте репозиторий:
    ```bash
    git clone https://github.com/TatyanaGurtovenko/lab_10_otrpo
    cd lab_10_otrpo
    ```


2. Установите необходимые зависимости:
    ```bash
    pip install psutil python-dotenv
    ```


3. Создайте файл .env в корневой папке проекта и добавьте в него следующие переменные:
    ```bash
      EXPORTER_HOST=
      EXPORTER_PORT=
    ```

4. Для сбора метрик Prometheus’ом необходимо добавить в конфигурацию Prometheus (prometheus.yml) следующую секцию:
    ```bash
       scrape_configs:
      - job_name: "custom_exporter"
        metrics_path: '/'
        static_configs:
          - targets: ["localhost:8081"]
    ```
    
5. Перейдите на http://localhost:9090

PromQL-запросы
  Использование процессора (в процентах):
 ```bash
   cpu_usage
 ```
  Всего памяти (в байтах):
 ```bash
   memory_total
 ```
 Используемая память (в байтах):
 ```bash
   memory_used
 ```
 Всего дискового пространства (в байтах):
 ```bash
   disk_total
 ```
 Используемое дисковое пространство (в байтах):
 ```bash
   disk_used
 ```
