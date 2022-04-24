# `tap-rickandmorty`

RickAndMorty tap class.

Built with the [Meltano SDK](https://sdk.meltano.com) for Singer Taps and Targets.

## Capabilities

* `catalog`
* `state`
* `discover`
* `about`
* `stream-maps`
* `schema-flattening`

## Settings

| Setting             | Required | Default | Description |
|:--------------------|:--------:|:-------:|:------------|
| start_date          | False    | None    | The earliest record date to sync |
| api_url             | False    | https://rickandmortyapi.com/api | The url for the API service |
| stream_maps         | False    | None    | Config object for stream maps capability. |
| stream_map_config   | False    | None    | User-defined config values to be used within map expressions. |
| flattening_enabled  | False    | None    | 'True' to enable schema flattening and automatically expand nested properties. |
| flattening_max_depth| False    | None    | The max depth to flatten schemas. |

A full list of supported settings and capabilities is available by running: `tap-rickandmorty --about`

## Installation

```bash
pipx install git+https://github.com/aaronsteers/tap-rickandmorty.git
```

### Source Authentication and Authorization

This tap runs fine with zero config. No auth is needed! 🙌

## Usage

You can easily run `tap-rickandmorty` by itself or in a pipeline using [Meltano](www.meltano.com).

### Executing the Tap Directly

```bash
tap-rickandmorty --version
tap-rickandmorty --help
tap-rickandmorty --config CONFIG --discover > ./catalog.json
```

## Developer Resources

- [ ] `Developer TODO:` As a first step, scan the entire project for the text "`TODO:`" and complete any recommended steps, deleting the "TODO" references once completed.

### Initialize your Development Environment

```bash
pipx install poetry
poetry install
```

### Create and Run Tests

Create tests within the `tap_rickandmorty/tests` subfolder and
  then run:

```bash
poetry run pytest
```

You can also test the `tap-rickandmorty` CLI interface directly using `poetry run`:

```bash
poetry run tap-rickandmorty --help
```

### Testing with [Meltano](meltano.com)

_**Note:** This tap will work in any Singer environment and does not require Meltano.
Examples here are for convenience and to streamline end-to-end orchestration scenarios._

Your project comes with a custom `meltano.yml` project file already created. Open the `meltano.yml` and follow any _"TODO"_ items listed in
the file.

Next, install Meltano (if you haven't already) and any needed plugins:

```bash
# Install meltano
pipx install meltano
# Initialize meltano within this directory
cd tap-rickandmorty
meltano install
```

Now you can test and orchestrate using Meltano:

```bash
# Test invocation:
meltano invoke tap-rickandmorty --version
# OR run a test `elt` pipeline:
meltano elt tap-rickandmorty target-jsonl
```

### Singer SDK Dev Guide

See the [dev guide](../../docs/dev_guide.md) for more instructions on how to use the Singer SDK to 
develop your own taps and targets.
