# Django 

## Como mostrar ipython
```python manage.py shell -i ipython```

## Como encerrar migrations:
```
find . -path “###/migrations/###.py” -not -name “__init__.py” -delete
find . -path “###/migrations/###.pyc” -delete
```

## Alterando um Dockerfile
```
# pull the official base image
FROM python:3

# set environment variables
ENV PYTHONUNBUFFERED 1

# set work directory
WORKDIR /app

ADD . /app

COPY . /requirements.txt /app/requirements.txt

# install dependencies
RUN pip install -r requirements.txt

# copy project
COPY . /app

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

## Criando

### ```mkdir django_project && cd django_project```
### ```virtualenv .ENV```
### ```source .ENV/bin/activate
### ```pip install Django```
### ```django-admin startproject project```
### ```python manage.py startapp app1```
### Em settings.py
```
 # Application definition

 INSTALLED_APPS = [
     'django.contrib.admin',
     'django.contrib.auth',
     'django.contrib.contenttypes',
     'django.contrib.sessions',
     'django.contrib.messages',
     'django.contrib.staticfiles',
+    'app'
 ]
```
### Em app1/views.py
```
 from django.shortcuts import render
+from django.http import HttpResponse

+def index(request):
+    return HttpResponse("Hello, World!")
```
### ```touch app1/urls.py```
### Em app1/urls.py:
```
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]

```
### Em project/urls.py
```
 from django.contrib import admin
-from django.urls import path
+from django.urls import include, path

 urlpatterns = [
+    path('', include('app.urls')),
     path('admin/', admin.site.urls),
 ]
```
## API
https://dev.to/xarala221/how-to-consume-restful-apis-with-django-the-easiest-way-4330
https://www.gauravvjn.com/write-json-apis-in-pure-django-for-beginners/
https://dev.to/codespresso/build-the-rest-api-using-python-django-part-4-nlp
https://dev.to/makiolo/django-model-frontend-crud-pagination-api-rest-filters-by-example-48d3
https://dev.to/jkaylight/django-rest-framework-authentication-with-dj-rest-auth-4kli
https://stackless.tech/document-and-test-django-apis-with-swagger-part-3/
https://dev.to/rajeshj3/document-and-test-django-apis-with-swagger-part-1-2le7
https://dev.to/itz_salemm/how-to-build-your-first-api-in-django-mi9
https://ozenero.com/django-restapis-postgresql-example-django-rest-framework-tutorial
https://dev.to/iamtekson/generate-api-docs-for-django-rest-framework-1cke
https://www.ordinarycoders.com/blog/article/django-ngrok
https://dev.to/balt1794/django-rest-api-crud-tutorial-2894
https://dev.to/apcelent/json-web-token-based-authentication-backend-for-django-project-3n90#comments
https://dev.to/apcelent/json-web-token-tutorial-with-example-in-python-23kb


## Banco
https://dev.to/anuragrana/15-articles-you-must-read-if-you-are-building-a-website-in-python-django-pp2
https://dev.to/saschalalala/aggregation-in-django-jsonfields-4kg5

## BOILERPLATE
https://github.com/rg3915/django-boilerplate/
https://github.com/rg3915/estoque
https://github.com/pydanny/cookiecutter-django
https://github.com/jazzband/django-debug-toolbar
https://github.com/jazzband/django-silk

## CELERY / REDIS
https://dev.to/okteto/develop-a-django-celery-app-in-kubernetes-3apk
https://dev.to/idrisrampurawala/deploying-django-with-celery-and-redis-on-ubuntu-3fo6
https://dev.to/valentinogagliardi/asynchronous-tasks-in-django-with-django-q-22ch
https://dev.to/valentinogagliardi/video-asynchronous-tasks-in-django-with-django-q-part-3-1knf
https://dev.to/paqman85/monitoring-celery-on-heroku-with-flower-2je8
https://dev.to/botreetech/implementing-celery-and-redis-with-django-for-background-task-processing-3g55
https://dev.to/magesh236/build-url-shortener-api-in-django-redis-gj8
https://dev.to/daeenchoi/understanding-celery-and-creating-simple-task-in-django-3gdk
https://dev.to/lukasklein/debouncing-a-celery-task-6pl
https://dev.to/iamtekson/django-with-celery-in-production-cb5
https://dev.to/iamtekson/celery-task-progress-bar-in-react-4ane
https://dev.to/a1k89/how-to-install-and-configure-celery-for-django-4o8e
https://dev.to/aishahsofea/dynamically-change-beat-schedule-with-djangocelerybeat-2aia
https://dev.to/lukasklein/debouncing-a-celery-task-6pl
https://dev.to/iamtekson/django-with-celery-in-production-cb5
https://dev.to/daeenchoi/database-scheduler-with-celery-beat-and-manage-schedule-in-django-admin-il5
https://dev.to/a1k89/making-django-s-signals-async-with-celery-1lb5
https://dev.to/danihodovic/monitoring-django-apps-mal

## CRUD
https://gist.githubusercontent.com/rg3915/b363f5c4a998f42901705b23ccf4b8e8/raw/4e6265f9b00792e29d71175796ac701f010e7865/boilerplatesimple.sh
https://gist.githubusercontent.com/liviocunha/a0170fb0c5b04cbf8f19a444c622359a/raw/d6f64b86afef5b94bb2de5b2b9ad3f0ac3cb8c7e/boilerplatesimple.sh
https://gist.github.com/rg3915/48ee1a226b19c6a9f1250952af5cdb6b
https://dev.to/thalesbruno/django-projeto-generico-com-bootstrap-3d86
https://dev.to/dinoperovic/headless-e-commerce-framework-for-django-4akh
https://dev.to/thearjun/integrate-django-jazzmin-theme-to-django-admin-adminlte-dashboard-5aao
https://dev.to/yahaya_hk/how-to-populate-your-database-with-data-from-an-external-api-in-django-398i
https://dev.to/sankalpjonna/building-a-django-crud-application-in-minutes-5g0p
https://dev.to/madhubankhatri/crud-with-django-119l
https://dev.to/developerroad/create-your-first-django-app-hello-world-app-3k52
https://dev.to/mungaigikure/simple-django-crud-app-4akc
https://dev.to/silicosis/tutorial-de-cookiecutter-django-y-deploy-con-docker-compose-en-linux-de5
https://dev.to/undefinedzack/how-to-create-a-to-do-app-in-django-with-bootstrap-and-font-awesome-nb2
https://dev.to/phantomraa/lifeknifex-a-collection-of-life-management-tools-49n3
https://github.com/kritebh/django-boilerplate-shell-script
https://github.com/app-generator/cookiecutter-django
https://dev.to/rshalford/django-creating-an-app-4hbe
https://dev.to/sm0ke/django-react-boilerplate-with-free-samples-6n8
https://github.com/kritebh/django-boilerplate-shell-script
https://dev.to/buckldav/django-person-image-generator-29c8
https://dev.to/luvpreet33/dockerizing-a-django-application-1ia1
https://dev.to/jonathanfarinloye/models-views-templates-lesson-5-266n

## Devops
https://dev.to/herchila/enable-debugging-in-a-django-project-with-docker-2550
https://dev.to/briancaffey/setting-up-a-django-project-in-kubernetes-with-minikube-3k8i
https://dev.to/hasurahq/how-to-write-dockerfiles-for-python-web-apps-5bmn
https://dev.to/xarala221/how-to-build-production-ready-application-with-django-and-postgresql-2cpi
https://dev.to/mojemoron/how-to-connect-your-django-app-to-a-dockerized-postgresql-and-pgadmin-133o
https://dev.to/sanchitsharma/data-analysis-setup-on-django-data-on-single-machine-57nn
https://dev.to/sibyx/customizable-database-based-reporting-o0a
https://dev.to/mattdsegal/how-to-automate-your-postgres-database-backups-54p9
https://dev.to/xarala221/how-to-become-more-productive-using-makefile-579b
https://dev.to/aymanemx/building-a-full-text-search-app-using-django-docker-and-elasticsearch-3bai
https://dev.to/pmutua/working-with-multiple-containers-using-docker-compose-on-linux-2299
https://dev.to/shrey27tri01/my-first-ever-github-action-1lh4
https://dev.to/pawamoy/django-application-as-an-authentication-authorization-server-for-shiny-3cfa
https://dev.to/courseprobe/django-project-structure-best-practice-2eeh
https://dev.to/skriptmonkey/deploying-wagtail-on-centos8-with-mariadb-nginx-gunicorn-3d6f
https://dev.to/anujdev/django-development-using-docker-as-host-part-5-django-development-27bj
https://dev.to/ashiqursuperfly/setting-up-the-database-dockerizing-django-for-deploying-anywhere-3emg
https://dev.to/itz_salemm/create-your-first-django-dockerised-app-3emk
https://dev.to/sm0ke/django-docker-open-source-projects-3g0j
https://dev.to/itz_salemm/create-your-first-django-dockerised-app-3emk
https://dev.to/ashiqursuperfly/setting-up-the-database-dockerizing-django-for-deploying-anywhere-3emg

## HOST FREE Heroku
https://dev.to/marcbeaujean/deploying-my-django-react-boilerplate-to-heroku-25je
https://dev.to/soumyaranjannaik/automatically-deploying-django-app-to-pythonanywhere-through-github-282j
https://dev.to/mh_shifat/host-your-django-project-in-pythonanywhere-free-3m4f
https://render.com/docs/deploy-django
https://tutorial.djangogirls.org/en/deploy/
https://help.pythonanywhere.com/pages/DeployExistingDjangoProject
https://dev.to/msambassadorske/serverless-python-on-azure-django-on-app-service-3fa
https://dev.to/brian101co/in-depth-guide-to-deploying-a-django-project-to-pythonanywhere-2od6
https://dev.to/ritza/creating-and-hosting-a-basic-web-application-with-django-and-repl-it-59l9
https://dev.to/highcenburg/how-to-deploy-your-django-app-to-heroku-for-free-1cf1
https://dev.to/magesh236/django-news-app-deployment-on-heroku-2k9o
https://dev.to/dilutewater/deploy-django-site-on-qovery-for-free-2gfk
https://dev.to/theshubhagrwl/deploying-django-app-to-heroku-full-guide-4ce0
https://dev.to/serhatteker/deployment-django-on-heroku-with-a-different-branch-314c
https://dev.to/undefinedzack/how-to-deploy-a-django-app-to-heroku-3k6i
https://dev.to/thirashapraween/django-easy-deployment-on-heroku-15jo
https://dev.to/developerroad/tutorial-deploying-a-django-app-on-heroku-4k6o
https://dev.to/developerroad/set-up-a-postgresql-database-in-django-4a1o
https://dev.to/shivamrohilla/deploy-django-project-on-heroku-2mne
https://dev.to/rabbilyasar/how-to-deploy-django-app-to-heroku-the-simple-way-21mh
https://dev.to/mdrhmn/deploying-django-web-app-using-heroku-updated-1fp
https://dev.to/imanaspaul/how-to-deploy-your-django-app-to-heroku-1k51
https://dev.to/manarabdelkarim/deploy-django-project-on-heroku-using-heroku-cli-460h
https://dev.to/rockandnull/change-django-database-backend-in-existing-projects-3c8k
https://dev.to/vigo/django-model-best-practices-3e8e

## Projetos/Repositorios
https://dev.to/jackdlinke/modern-django-project-examples-58mm
https://dev.to/djangonews/django-news-16-wagtail-roadmap-lots-of-django-a-new-ish-js-framework-that-we-like-and-more-working-remote-tips-5an3#comments
https://dev.to/djangonews/issue-38-new-release-of-black-wagtail-2-10-1-articles-and-adding-flame-graphs-to-django-debug-toolbar-92f
https://dev.to/magbanum/octoprofile-the-django-project-43oj
https://dev.to/ramkumarm15/4-useful-django-packages-29gk
https://github.com/ShivamRohilllaa/students
https://github.com/ShivamRohilllaa/E-learning-Django-
http://www.findyourapi.com/
https://ozenero.com/python-tutorials
https://dev.to/madhubankhatri/create-your-own-youtube-video-downloader-using-youtubedl-django-1646
https://dev.to/lewiskori/user-authentication-with-jwts-in-a-django-and-vue-js-multi-tenant-app-4p9o
https://dev.to/shubham1710/build-a-social-media-website-with-django-part-5-feed-app-templates-174i
https://dev.to/phantomraa/stopclutch-a-django-race-manager-aee

## Recursos/Truques
https://dev.to/lewiskori/how-to-create-custom-commands-in-django-k9b
https://dev.to/foadmoha/creating-custom-manage-py-commands-for-django-33cc
https://dev.to/nishantwrp/google-apis-oauth-in-django-17ch
https://dev.to/benhammondmusic/how-to-connect-google-calendar-api-to-django-on-heroku-3834
https://hakibenita.medium.com/how-to-turn-django-admin-into-a-lightweight-dashboard-a0e0bbf609ad
https://simpleisbetterthancomplex.com/tutorial/2018/01/18/how-to-implement-multiple-user-types-with-django.html
https://hakibenita.medium.com/how-to-add-custom-action-buttons-to-django-admin-8d266f5b0d41
https://dev.to/danihodovic/integrating-chart-js-with-django-admin-1kjb
https://dev.to/nick_langat/how-to-use-charts-to-visualize-django-models-162k
https://simpleisbetterthancomplex.com/tutorial/2020/01/19/how-to-use-chart-js-with-django.html
https://simpleisbetterthancomplex.com/tutorial/2018/04/03/how-to-integrate-highcharts-js-with-django.html
https://dev.to/sm0ke/django-create-pdf-148f
https://dev.to/ashraf_zolkopli/django-recaptha-everywhere-1474
https://dev.to/ashraf_zolkopli/django-defense-against-bot-42ib
https://dev.to/ashraf_zolkopli/decoupling-django-secret-key-65d
https://dev.to/lymaa/working-with-geo-django-32nd
https://dev.to/mhihasan/geodjango-installation-postgis-and-gdal-36h1
https://dev.to/pauloxnet/maps-with-django-part-1-geodjango-spatialite-and-leaflet-2bn2
https://dev.to/aravindas4/django-decouple-excerpt-4c9j
https://dev.to/mblayman/make-a-hugo-static-blog-inside-a-django-app-38gj
https://dev.to/tomaszd/see-all-raw-sql-queries-in-django-3lh0
https://dev.to/madhubankhatri/sending-emails-in-django-2b22
https://dev.to/highcenburg/sending-dynamic-emails-from-a-centralized-mailer-21fk
https://dev.to/djangotricks/guest-post-sending-emails-with-django-7d3
https://dev.to/ninjasoards/resize-image-on-save-in-django-before-sending-to-amazon-s3-no-lambda-function-required-23f2
https://dev.to/madhubankhatri/how-to-use-ckeditor-in-django-2igi
https://github.com/app-generator/django-datatables-sample
https://dev.to/djangodoctor/what-django-best-practices-is-django-breaking-4e2p
https://dev.to/ashraf_zolkopli/django-allauth-1lc6
https://dev.to/mmoallemi99/serverless-micro-django-lightweight-yet-powerful-python-utility-for-lambda-functions-1dp5
https://dev.to/redhap/tenant-schema-turbocharge-35bf
https://dev.to/hevalhazalkurt/using-environment-files-in-django-3m8o
https://dev.to/chryz_codez/django-json-response-safe-false-4f9i
https://dev.to/balt1794/method-str-explained-using-django-admin-panel-1nde
https://dev.to/a1k89/resize-image-before-save-in-django-2b40
https://dev.to/rammyblog/how-to-create-multiple-independent-admin-sites-in-django-1klh
https://dev.to/pgorecki/introducing-django-cancan-authorization-library-for-django-1d2f
https://dev.to/yahaya_hk/crispy-forms-in-django-9kp
https://dev.to/danielfeldroy/django-slug-id-url-design-3l8b
https://dev.to/brightside/scheduling-tasks-using-apscheduler-in-django-2dbl
https://dev.to/victoria/manipulating-data-with-django-migrations-dmf
https://dev.to/balt1794/chapter-6-navbar-3oej
https://dev.to/gilbishkosma/custom-context-processors-in-django-3c93
https://medium.com/analytics-vidhya/integrating-elasticsearch-7-to-django-project-c3812de78246
https://dev.to/daveson217/how-to-create-an-other-field-in-html-select-using-django-51ln
https://dev.to/txiocoder/creating-image-from-dataurl-base64-with-pyhton-django-454g
https://dev.to/valerybriz/django-queries-optimization-10ji
https://dev.to/lquenti/dynamic-group-based-ldap-authentication-with-django-and-regex-1h4p
https://dev.to/harveyhalwin/building-your-own-template-tags-in-django-21la
https://dev.to/feldroy/adding-metadata-to-pdfs-3adl
https://dev.to/lucascastejon/create-a-easy-test-using-model-baker-4p4m
https://dev.to/lucasmagnum/djangotip-select-prefetch-related-402i
https://dev.to/psteph/how-to-quickly-prototype-hibernate-or-django-model-classes-from-a-json-object-91m
https://dev.to/singh1114/how-to-use-factoryboy-to-create-model-instances-in-django-for-testing-36j3
https://dev.to/asdrubalsantander/setting-up-pytest-for-a-django-project-3362
https://dev.to/bnevilleoneill/do-you-need-graphql-with-django-1o6b
https://dev.to/kite/django-templates-best-practices-1e25
https://dev.to/coderasha/how-to-migrate-data-from-sqlite-to-postgresql-in-django-182h
https://dev.to/mehdipourfar/faster-csv-export-with-django-postgres-5bi5
https://dev.to/arsho/writing-django-custom-command-1dl0
https://dev.to/bencleary89/using-enums-as-django-model-choices-4dk5
https://dev.to/mkdev/how-to-cover-django-application-with-unit-tests-4ei3
https://dev.to/ppshobi/-email-sending-in-django-2-part--1--1i0a
https://dev.to/adamghill/searching-within-an-area-with-geodjango-and-postgis-24g8
https://docs.python.org/3/library/inspect.html

## Segurança/Perfomance
https://dev.to/victoria/django-project-best-practices-to-keep-your-developers-happy-23e4
https://dev.to/djangodoctor/migration-breaking-3cl6
https://dev.to/djangodoctor/why-queryset-exists-is-more-efficient-than-queryset-count-2f3h
https://dev.to/djangodoctor/fixing-django-anti-patterns-in-sentry-m4f
https://dev.to/djangodoctor/remove-tech-debt-from-your-django-codebase-in-seconds-2ab0
https://dev.to/djangodoctor/hacking-django-websites-session-hijacking-with-xss-2l8o
https://dev.to/djangodoctor/666-django-projects-checked-for-inefficient-database-queries-over-half-had-these-4-anti-patterns-4383
https://dev.to/djangodoctor/22-of-django-websites-can-t-roll-back-prod-thanks-to-these-2-mistakes-4cln
https://dev.to/djangodoctor/20-of-django-websites-are-vulnerable-to-these-3-hacks-3fd1
https://dev.to/djangodoctor/40-of-django-projects-have-these-url-bugs-waiting-to-happen-218c
https://dev.to/djangodoctor/importing-settings-files-directly-is-more-common-than-you-think-d4c
https://dev.to/djangodoctor/hidden-in-plain-sight-8-of-django-projects-have-broken-middleware-order-54bm
https://dev.to/djangodoctor/48-of-django-projects-could-simplify-models-py-in-these-3-ways-1anc
https://dev.to/djangodoctor/53-of-django-projects-have-redundant-code-594l

## Templates
https://dev.to/sm0ke/django-boilerplate-code-open-source-and-free-2aa5
https://dev.to/sm0ke/django-boilerplate-argon-open-source-app-coded-in-python-3l1k
https://dev.to/sm0ke/django-dashboard-black-open-source-boilerplate-code-38kh
https://dev.to/sm0ke/material-dashboard-lite-version-coded-in-flask-and-django-225b
https://dev.to/sachinchaurasiya/customizing-colors-django-admin-panel-1n4h
https://dev.to/sm0ke/adminkit-a-modern-bootstrap-5-template-now-available-in-flask-and-django-5aj4
https://dev.to/sm0ke/django-templates-short-introduction-and-free-samples-2878
https://dev.to/sm0ke/django-a-curated-list-with-useful-oss-projects-24bc
https://dev.to/sm0ke/django-bootstrap-5-volt-dashboard-free-product-non
https://dev.to/themesberg/show-dev-free-django-dashboard-admin-template-3be9
https://dev.to/sm0ke/soft-ui-dashboard-bootstrap-5-free-django-template-29dj
https://dev.to/admindashboards/soft-ui-generate-a-django-dashboard-with-ease-4i05
https://dev.to/sm0ke/django-volt-dashboard-free-dashboard-built-with-django-3-2-0-lts-2cg3
https://dev.to/sm0ke/django-website-templates-free-download-4m62
https://dev.to/sm0ke/django-graphs-and-charts-argon-dashboard-1p0b
https://dev.to/sm0ke/django-admin-dashboards-open-source-and-free-1o80

## VSCODE
https://dev.to/developerroad/best-vscode-extensions-for-python-developers-525c
https://dev.to/katsuya_9/remote-debug-django3-docker-with-vscode-3k9c
https://dev.to/felipepanegalli/migrando-do-pycharm-para-o-vscode-f7m
https://dev.to/wealize/debug-python-and-django-easily-from-visual-studio-code-4dfk
https://dev.to/pzelnip/visual-studio-code-tasks-and-split-terminals-2ghk
https://dev.to/endlesstrax/writing-my-first-vs-code-extension-1e3n

## Webscrap
https://dev.to/julbrs/the-web-is-an-api-scrap-it-4ofb
https://dev.to/rooky1905/zomato-web-scraper-2jb6
https://dev.to/mdrhmn/web-scraping-using-django-and-selenium-3ecg
https://dev.to/madhubankhatri/create-a-dictionary-app-using-django-and-beautifulsoup-5gd5
https://dev.to/chukslord1/how-to-build-a-soccer-data-web-scraper-with-django-and-fauna-2l1o
