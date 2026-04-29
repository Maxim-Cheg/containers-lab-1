FROM alpine:latest
# Установка CA сертификатов для HTTPS
RUN apk --no-cache add ca-certificates
# Рабочая директория
WORKDIR /root/
# Копирование собранного приложения из builder
COPY --from=builder /app/main .
# Копирование статических файлов
COPY --from=builder /app/static ./static
# Экспонирование порта
EXPOSE 8080
# Запуск приложения
CMD ["./main"]