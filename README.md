# appduct

## Synopsis

Support server-side web application for Mewduct

## Description

Appduct is the server-side application required to use the optional features of Mewduct that cannot function without a server-side application.

Currently, it provides only the reaction feature.

## Dependencies

* Elixir >~ 1.18
* Elixir modules
    * Bandit
    * CubDB
    * RemoteIp

## Install

* `git clone https://github.com/reasonset/mewduct-appduct.git`
* (Optional) Copy `config/config.exs` to `config/runtime.exs` and edit it
* `mix deps.get`
* Write http route to appduct`/reaction`

## Start

```bash
mix server
```

## Hints

Appduct has `/reaction/` as a valid request path prefix. By proxying this location to Appduct, it can operate on the same domain as Mewduct.

Appduct places a JSON file for each reaction in the `<db>/<user_id>/<media_id>` directory. If the number of reactions is extremely high, the files may overflow.

In that case, since Appduct does not reference these JSON files, you may archive or move them.

## Provided endpoints

### `POST /reaction/plusone`

Mewduct's `reaction_post_to` endpoint

### `GET /reaction/reactions`

Mewduct's `reaction_get_from` endpoint
