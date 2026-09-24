{{if eq .unresolved_count 1}}The story-mode review finished with 1 unresolved comment.{{else}}The story-mode review finished with {{.unresolved_count}} unresolved comments.{{end}}

{{if not .change_url}}Story mode is an editorial view over the underlying diff. Address the comments against the actual source files. Do not edit, regenerate, or patch the saved story JSON unless the user explicitly asks for that.

{{end}}{{if .comments_unresolved_json}}{{.comments_unresolved_json}}

{{end}}{{if .change_url}}These comments are review feedback on {{if eq .forge "gitlab"}}merge request !{{.change_number}}{{else}}pull request #{{.change_number}}{{end}} ({{.change_url}}). Post them there by running:

  crit push --forge {{.forge}} {{.change_url}}

Do not edit any files, or the saved story JSON, unless the user asks you to.{{else if eq .internal_session_mode "plan"}}Revise the plan to address each comment. To reply to comments, use `crit comment --plan {{.plan_slug}} --reply-to <id> --author <your-name> "<explanation>"`.{{else}}For each comment, make any needed code edit and reply explaining what you did using `crit comment --reply-to <comment-id> --author <your-name> "<explanation>"`.{{end}}{{if and .next_round_cmd (not .change_url)}}

When you're done, run:

  {{.next_round_cmd}}{{end}}
