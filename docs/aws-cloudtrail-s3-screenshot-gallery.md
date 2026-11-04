# AWS CloudTrail and S3 — Splunk Screenshot Gallery

These screenshots come from my cybersecurity training log review. I organized them in the order I worked through the searches so the steps are easy to follow.

**Context:** The log data is historical. These images help illustrate my queries and follow-up checks; they do not prove a confirmed breach or data theft.

| # | Evidence | What it shows |
| --- | --- | --- |
| 1 | [CloudTrail identity types](../images/aws-cloudtrail-s3-review/01-cloudtrail-identity-types.png) | Event counts grouped by user type |
| 2 | [IAM user activity](../images/aws-cloudtrail-s3-review/02-cloudtrail-iam-users.png) | Counts for four named training identities |
| 3 | [Available Splunk sourcetypes](../images/aws-cloudtrail-s3-review/03-available-sourcetypes.png) | The log sources available for correlation |
| 4 | [Hardware inventory](../images/aws-cloudtrail-s3-review/04-hardware-hosts.png) | Three hosts found in the hardware logs |
| 5 | [Hardware details](../images/aws-cloudtrail-s3-review/05-host-hardware-details.png) | CPU, drive, and memory fields returned for those hosts |
| 6 | [Bucket ACL search](../images/aws-cloudtrail-s3-review/06-bucket-acl-search.png) | Two CloudTrail PutBucketAcl events |
| 7 | [Narrowed ACL search](../images/aws-cloudtrail-s3-review/07-narrowed-acl-search.png) | One matching event after restricting the time window |
| 8 | [S3 text filter](../images/aws-cloudtrail-s3-review/08-s3-text-search-no-results.png) | A search that returned no matching events |
| 9 | [S3 ACL and policy lookups](../images/aws-cloudtrail-s3-review/09-bucket-api-access.png) | GET requests for bucket ACL and policy information |
| 10 | [S3 PUT activity](../images/aws-cloudtrail-s3-review/10-s3-put-object-events.png) | Object uploads and an ACL-related operation |
| 11 | [First archive-size query](../images/aws-cloudtrail-s3-review/11-object-size-search-no-results.png) | A query that returned no results |
| 12 | [Time-scoped archive query](../images/aws-cloudtrail-s3-review/12-object-size-time-scoped-no-results.png) | A second query that returned no results |
| 13 | [Archive-size results](../images/aws-cloudtrail-s3-review/13-object-size-successful-query.png) | Access entries with populated object-size fields |
| 14 | [Windows process logs](../images/aws-cloudtrail-s3-review/14-process-log-events.png) | Windows process monitoring records |
| 15 | [Process instance summary](../images/aws-cloudtrail-s3-review/15-processor-metrics.png) | Process names and processor metric fields |
| 16 | [Sysmon details](../images/aws-cloudtrail-s3-review/16-windows-sysmon-event.png) | Expanded Windows Sysmon XML event fields |

## Main write-up

[Read the investigation and its conclusions](../cases/03-aws-cloudtrail-s3-review.md).

**Investigation status:** Inconclusive / requires further validation. Absence of results in a particular search is not proof that an event did not occur.
