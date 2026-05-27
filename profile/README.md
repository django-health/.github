# django-health

Django apps for integrating health and fitness data into your applications.

`django-health` is a collection of pluggable Django packages that handle the unglamorous parts of working with health data — modeling activity, sleep, biometrics, and workouts; talking to vendor APIs; normalizing units; and keeping it all queryable. Drop them into a new project or an existing Django app.

## Packages

### [django-healthdatamodel](https://github.com/django-health/django-healthdatamodel)
The foundation. A normalized data model for health and fitness metrics — heart rate, sleep stages, workouts, steps, body composition, and more — with sensible defaults for units, time zones, and provenance tracking. Other packages in this org build on it, but it stands alone.

### [django-whoop](https://github.com/django-health/django-whoop)
WHOOP API integration. Handles OAuth, webhook delivery, and syncing recovery, strain, sleep, and workout data into your `django-healthdatamodel` tables.

### [django-google-health](https://github.com/django-health/django-google-health)
Google Health Connect and Fit integration. Pulls activity, sleep, and biometric data from the Google ecosystem and maps it into the shared data model.

More integrations are in progress — see individual repos for status.

## Design principles

- **One data model, many sources.** Vendor integrations normalize into `django-healthdatamodel` so your application code doesn't care whether a heart rate sample came from a WHOOP strap or a Pixel Watch.
- **Pluggable, not prescriptive.** Each package is independently installable. Use one, use all of them, or fork what you need.
- **Honest about provenance.** Every metric carries its source, device, and confidence where the vendor provides it. No silent merging of incompatible measurements.
- **Django-native.** Standard apps, standard migrations, standard ORM. No surprise infrastructure requirements.

## Project status

Packages are at different maturity levels. Each repo's README states its current status, supported Django and Python versions, and any production caveats. In general:

- Treat anything pre-1.0 as evolving — APIs may change between minor versions.
- Pinned dependencies and migration notes live in each repo.
- Issues and PRs are welcome across all packages.

## Getting started

Pick the integration you need and follow its README. Most packages expect a recent Django (4.2+) and Python (3.10+). `django-healthdatamodel` is a dependency of the integration packages and will be installed automatically.

## Contributing

Contributions are welcome — new vendor integrations especia
