#!/bin/sh

APP_NAME="hello-servlet-app"

case "$1" in
    start)
        /sbin/start-stop-daemon -S -b -m -d ./ -p ${APP_NAME}.pid -x /usr/bin/java -- -jar ${APP_NAME}.jar
        echo "Hello servlet started"
        ;;
    restart)
        /sbin/start-stop-daemon -K -p ${APP_NAME}.pid &>/dev/null
        /sbin/start-stop-daemon -S -b -m -d ./ -p ${APP_NAME}.pid -x /usr/bin/java -- -jar ${APP_NAME}.jar
        echo "Hello servlet restarted"
        ;;
    stop)
        /sbin/start-stop-daemon -K -p ${APP_NAME}.pid &>/dev/null
        echo "Hello servlet stopped"
        ;;
    *)
        echo "Usage: $0 start|stop application" >&2
        exit 3
        ;;
esac

