# Cookbook Quality Metrics

This is a system used to provide an objective measure of a number of cookbook
quality metrics.  The system takes inspiration from [Foodcritic](http://www.foodcritic.io/).

This repository is a place where the community can start collaborating on
metrics.

## Proposing New Metrics

* create a new branch in this repository
* copy `quality-metrics/template.md` to `quality-metrics/new/qm-000-SHORT_NAME.md`
* Add new metric to your new file
* Submit a pull request against this repository

## Approving New Metrics

* New metrics will be reviewed by the people listed in `MAINTAINERS.md`
* A simple majority of MAINTAINERS must approve each new rule with a :+1:
* An EDITOR (someone listed in `EDITORS.md`) will:
  * Assign a number to the quality metric by updating the name of the file and the `SMQM` field
  * Move the file from `quality-metrics/new` to `quality-metrics/`
  * Update the status to `Accepted`

The metric's status should be changed to `Implemented` when the metric is being measured on the [public Supermarket](https://supermarket.chef.io).

## Viewing Cookbook Scores

The [Supermarket](https://supermarket.chef.io) will show a total score for each cookbook.

Each cookbook listed on the Supermarket will have a tab showing how it's score was generated.

## Maintenance Policy

This project generally follows [Chef's Maintenance Policy](https://github.com/chef/chef-rfc/blob/master/rfc030-maintenance-policy.md).

* The **Project Lead** for this is project is the current project lead for [Chef](https://github.com/chef/chef) as specified in the [MAINTAINERS file](https://github.com/chef/chef/blob/master/MAINTAINERS.md).

* The **Lieutenant** and **Maintainers** for this project are listed in `MAINTAINERS.md`.
