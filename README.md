# Music Cloud Gateway

Канонические nginx-конфиги Music Cloud:

- `default.conf` — HTTP.
- `tls.conf` — HTTPS + ACME + редирект.
- `locations.conf` — проксирование API, tus, Subsonic и отдача `/_media/`.
- `nginx-entrypoint.sh` — выбор конфига по `MC_TLS`, `envsubst` домена и периодический reload.

Сейчас образ `ghcr.io/moshms/web` собирается в репозитории `web` и содержит копию этих файлов, чтобы сборка была самодостаточной. При изменении конфигов синхронизируйте их с `web/nginx/` или переходите на cross-repo artifact.
