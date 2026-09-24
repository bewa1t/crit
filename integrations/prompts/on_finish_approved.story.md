{{if .change_url}}The story-mode review of {{if eq .forge "gitlab"}}merge request !{{.change_number}}{{else}}pull request #{{.change_number}}{{end}} ({{.change_url}}) finished with no open comments. There is nothing to push, and no files need changing.{{else}}Story-mode review approved. All comments are resolved.

Story mode is an editorial view over the underlying diff. Do not edit, regenerate, or patch the saved story JSON unless the user explicitly asks for that.{{end}}
