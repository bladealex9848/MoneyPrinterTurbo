# Guía de internacionalización (i18n)

MoneyPrinterTurbo soporta múltiples idiomas tanto en la interfaz WebUI como en los README del proyecto.

## Idiomas soportados

| Código | Idioma | Archivo |
|--------|--------|---------|
| `zh` | 简体中文 | `webui/i18n/zh.json` |
| `en` | English | `webui/i18n/en.json` |
| `es` | Español | `webui/i18n/es.json` |
| `de` | Deutsch | `webui/i18n/de.json` |
| `pt` | Português | `webui/i18n/pt.json` |
| `ru` | Русский | `webui/i18n/ru.json` |
| `tr` | Türkçe | `webui/i18n/tr.json` |
| `vi` | Tiếng Việt | `webui/i18n/vi.json` |

## Cómo funciona

1. La WebUI carga todos los archivos JSON en `webui/i18n/` al iniciar (`utils.load_locales`)
2. El selector de idioma en la parte superior muestra cada idioma disponible con su nombre nativo
3. La función `tr(key)` busca la traducción en el idioma seleccionado; si no existe, devuelve la clave original
4. El idioma de la UI se guarda en `config.ui["language"]` y persiste en `webui/.streamlit/webui.toml`

## Añadir un nuevo idioma

1. Copie `webui/i18n/en.json` como base
2. Renómbrelo con el código de idioma ISO 639-1 (ej: `fr.json`)
3. Traduzca todos los valores del campo `"Translation"` — no modifique las claves
4. Actualice el campo `"Language"` con el nombre nativo del idioma
5. Añada el locale al array `support_locales` en `webui/Main.py` si desea que aparezca como opción de idioma de guion de video
6. Añada el enlace al README correspondiente en `README.md` y `README-en.md`

## Estructura del archivo de traducción

```json
{
  "Language": "Nombre nativo del idioma",
  "Translation": {
    "clave original en inglés": "Traducción al idioma destino",
    ...
  }
}
```

- Las claves del objeto `"Translation"` son siempre en inglés (tomadas de `en.json`)
- Los valores son las traducciones al idioma destino
- Se soporta formato Markdown dentro de los valores (negritas, colores, enlaces)

## Convenciones

- Los archivos README siguen el patrón `README-{código}.md` (ej: `README-es.md`, `README-en.md`)
- El README principal (`README.md`) está en chino simplificado
- Todos los README enlazan entre sí en su cabecera de idiomas
