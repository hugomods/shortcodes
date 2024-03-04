{{- $name := .Get 0 }}
{{- $markdown := true }}
{{- if isset .Params 1 }}
  {{- $markdown = .Get 1 }}
{{- end }}
{{- with .Page.Resources.Get $name }}
  {{- cond $markdown (.Content | $.Page.RenderString) .Content }}
{{- end }}
