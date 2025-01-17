---
title: Schema Enforcer
github: 'https://github.com/PostHog/schema-enforcer-plugin'
installUrl: 'https://app.posthog.com/project/apps?name=Schema%20Enforcer'
thumbnail: >-
  https://res.cloudinary.com/dmukukwp6/image/upload/posthog.com/contents/cdp/thumbnails/schema-enforcer.png
tags:
  - schema-enforcer
---

import Requirements from "./_snippets/requirements.mdx"
import FeedbackQuestions from "./_snippets/feedback-questions.mdx"
import PostHogMaintained from "./_snippets/posthog-maintained.mdx"

The connector enables you to enforce a schema on events in PostHog as they are ingested. It does this by preventing ingestion if the event:

-   Is missing a required property
-   Has a property with the wrong type
-   Is not included in the file and `onlyIngestEventsFromFile` is true

It also:

-   Removes all other properties from an event except selected ones if acceptOnlySchemaProps is true
-   Configuration is done via a JSON file uploaded as an attachment

<Requirements />

## Installation

1. Log in to your PostHog instance
2.  Click "[Data pipeline](https://us.posthog.com/apps)" in the left sidebar
3. Search for 'Schema Enforcer'
4. Select the connector, press 'Install' and follow the on-screen instructions

## Configuration

Below is an example configuration file:

```
{
    "onlyIngestEventsFromFile": true,
    "eventSchemas": {
        "testEvent": {
            "acceptOnlySchemaProps": true,
            "schema": {
                "foo": {
                    "type": "string",
                    "required": false
                },
                "bar": {
                    "type": "number",
                    "required": true
                },
                "baz": {
                    "type": "boolean",
                    "required": false
                }
            }
        }
    }
}
```

## Additional configuration

<AppParameters />

## FAQ

### Is the source code for this connector available?

PostHog is open-source and so are all connectors on the platform. The [source code for the Schema Enforcer](https://www.npmjs.com/package/@posthog/schema-enforcer-plugin) is available on NPM.

### Who created this connector?

A lot of people worked on this app! We'd like to thank the following PostHog team members...

-   [Yakko Majuri](https://www.npmjs.com/~yakkomajuri)
-   [Marius Andra](https://www.npmjs.com/~mariusandra)
-   [James Greenhill](https://www.npmjs.com/~fuziontech)
-   [Michael Matloka](https://www.npmjs.com/~twixes)
-   [Alex Kim](https://www.npmjs.com/~alexkim205)
-   [Karl Aksel-Puulmann](https://www.npmjs.com/~macobo) and
-   [Tim Glaser](https://www.npmjs.com/~timgl)

For creating the Schema Enforcer. Thank you, all!

<PostHogMaintained />

<FeedbackQuestions />
