# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Drupal project. PHP is the main language. Dependencies are managed with Composer, and site-level commands (cache rebuilds, config import/export, database updates, etc.) go through Drush rather than direct database or filesystem edits.

## Coding standards

Follow Drupal coding standards for all PHP, YAML, JS, and CSS in this repo (see https://www.drupal.org/docs/develop/standards). If a linter/sniffer config (e.g. `phpcs.xml`, `phpstan.neon`) is present, run it before considering a change done.

## Common commands

- Install/update dependencies: `composer install` / `composer update`
- Rebuild caches: `drush cache:rebuild` (`drush cr`)
- Import/export configuration: `drush config:import` (`drush cim`) / `drush config:export` (`drush cex`)
- Run pending database updates: `drush updatedb` (`drush updb`)

## Database and configuration changes

Any change that touches the database (schema updates, `hook_update_N`, content/data migrations) or site configuration (`config/` YAML, config split, config import/export) is sensitive and must be called out explicitly for review — don't bundle it silently into an unrelated change, and flag it clearly in the PR description and commit message.

## Contributing conventions

`CONTRIBUTING.md` defines the intended workflow for changes in this repo:

- Create a branch per change (`git checkout -b my-change`) rather than committing directly to `main`.
- Keep pull requests small and focused on one thing.
- Write commit messages that explain *why* a change was made, not just *what* changed.
- Push the branch (`git push -u origin my-change`) and open a pull request against `main`.
