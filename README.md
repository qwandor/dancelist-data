# Dancelist data

This repository contains the data behind https://dance.q.geek.nz/, a list of social folk dance
events. Additions and corrections are welcome, subject to the listing policy below.

Code for the website itself is in a [separate repository](https://github.com/qwandor/dancelist).

## Listing policy

This list is for social folk dance events which are open to the public. This includes both regular
social dances, special one-off dances and multi-day events such as festivals.

| In scope                                                | Out of scope                                                      |
| ------------------------------------------------------- | ----------------------------------------------------------------- |
| Social folk dances, such as balfolk, contra and ceilidh | Performance dances, such as Morris                                |
|                                                         | Other styles of social dance, such as Lindy Hop, forró or tango   |
| Folk dance festivals                                    | Folk music festivals without a substantial social dance component |
| Regular or one-off social dance events with live music  | Concerts                                                          |
| Events open to the public                               | Private parties or clubs                                          |
| In-person events                                        | Online events                                                     |

## Format

Event data is in YAML format under [events](events/), with generally one file per location or
organisation. Each file may contain one or more events.

### Required fields

An event must have at least a name, a start date and end date (they may be the same), a country, a
city, at least one style, and at least one of `workshop` or `social` must be true. The first line of
the file should be a modeline referring to the [JSON schema](events_schema.json)). For example:

```yaml
# yaml-language-server: $schema=../events_schema.json
events:
  - name: Clandestine Mazurka in Northampton Square
    start_date: 2022-02-13
    end_date: 2022-02-13
    country: UK
    city: London
    styles: [balfolk]
    workshop: false
    social: true
```

### Optional fields

| Field name     | Usage                                                                                                                                |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `details`      | A longer description of the event, one sentence.                                                                                     |
| `links`        | One or more URLs with more information of the event. This should ideally include both a Facebook event page and a non-Facebook page. |
| `bands`        | A list of bands playing at the event.                                                                                                |
| `callers`      | A list of callers calling at the event, for called dances such as contra and ceilidh                                                 |
| `price`        | The price (or range of prices) of the event, including currency. e.g. "£5-15" or "free".                                             |
| `organisation` | The organisation who is running the event.                                                                                           |

For example:

```yaml
# yaml-language-server: $schema=../events_schema.json
events:
  - name: Bristol Contra Dance
    details: All welcome of any level of experience for great dancing to amazing gender-free calling and brilliant music.
    links:
      - "https://bristolcontra.wordpress.com/"
      - "https://www.facebook.com/events/690727345267580/"
    start_date: 2022-02-18
    end_date: 2022-02-18
    country: UK
    city: Bristol
    styles: [contra]
    workshop: false
    social: true
    bands:
      - Bearded Dragons
    callers:
      - Charlotte Rich-Griffin
    price: £6-£15
    organisation: Bristol Contra
```
