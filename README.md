# gohugo-partial-range-insert
Just showing how to insert a partial via a range loop over a data yaml file in [Hugo](https://gohugo.io/).

## What it is about
I want to replace this manual behaviour in `baseof.html`:
```html
    {{ partial "about.html" . }}

    {{ partial "projects.html" . }}

    {{ partial "about.html" . }}
```

With a loop (range) in the style of:
```html
    {{ range .Site.Data.home_sections }}
    {{ partial .file . }}
    {{ end }}
```

So the order of the sections can be defined via YAML (`home_sections.yml`):
```yml
- file: about.html

- file: projects.html

- file: about.html

- file: about.html
```

## Reference
The repo was created because I was facing an issue with this behaviour. But in this demo repo the issue didn't happend. So here you see, how it should work.

- My issue: https://discourse.gohugo.io/t/insert-partial-via-variable-from-range/56542