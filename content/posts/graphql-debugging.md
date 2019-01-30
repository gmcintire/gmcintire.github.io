---
title: "Graphql Debugging"
date: 2019-01-29T10:55:58-06:00
draft: false
---

https://hexdocs.pm/plug/Plug.Conn.html#register_before_send/2

`In your phoenix endpoint.ex`

```elixir
plug(:debug_response)

defp debug_response(conn, _) do
  Plug.Conn.register_before_send(conn, fn conn ->
    conn.req_body |> IO.inspect()
    conn
  end)
end
```