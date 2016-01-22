# Cookbook Quality Metrics

This is a system used to provide an objective measure of a number of cookbook
quality metrics.  The system takes inspiration from [Foodcritic](http://www.foodcritic.io/).

This repository is a place where the community can start collaborating on
metrics.

The lifecycle of a metric will be:

* *Draft* - this is a proposed metric, ready for community discussion and
  approval.
* *Accepted* - this metric has been accepted and merged into the master branch.
* *In Progress* - data for this metric is being gathered and is visible by some
  mechanism but not displayed on the Supermarket by default.
* *Implemented* - this metric has been implemented and is shown on the Supermarket.
* *Closed* - this metric has not been accepted or has been removed from the
  system.

## Proposing New Metrics

* create a new branch in this repository
* copy `quality-metrics/template.md` to `quality-metrics/new/qm-000-SHORT_NAME.md`
* Add new metric to your new file
* Submit a pull request against this repository

## Approving New Metrics

* New metrics will be reviewed by the people listed in `MAINTAINERS.md`
* At least two MAINTAINERS must approve each new metric with a :+1:
  * Any maintainer may :-1: a proposed metric.  This will increase the
    requirement for a metric to be merged to an absolute majority of maintainers.
* An EDITOR (someone listed in `EDITORS.md`) will:
  * Assign a number to the quality metric by updating the name of the file and
    the `SMQM` field
  * Move the file from `quality-metrics/new` to `quality-metrics/`
  * Update the status to `Accepted`
  * Add the metric to `SMQM.md`

The metric's status should be changed to `In Progress` once data is being gathered for that metric.

The metric's status should be changed to `Implemented` when the metric is being measured and is visible on the [public Supermarket](https://supermarket.chef.io).

## Viewing Cookbook Metrics

The [Supermarket](https://supermarket.chef.io) will show the metrics for each cookbook. We are currently concerned with coming up with a good list of cookbook quality metrics outside of the technical implementation. Once this moves into the implementation phase, there may be metrics here which require adjustments to Chef, Supermarket, or other tools.

## Maintenance Policy

This project generally follows [Chef's Maintenance Policy](https://github.com/chef/chef-rfc/blob/master/rfc030-maintenance-policy.md).

* The **Project Lead** for this is project is the current project lead for [Chef](https://github.com/chef/chef) as specified in the [MAINTAINERS file](https://github.com/chef/chef/blob/master/MAINTAINERS.md).

* The **Lieutenant** and **Maintainers** for this project are listed in `MAINTAINERS.md`.
