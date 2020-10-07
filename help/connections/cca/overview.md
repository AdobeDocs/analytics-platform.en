journey iq: cross-channel analytics

definition of stitching, and what it is not

This feature allows you to stitch together data sets which may include the merging of user data from authenticated and unauthenticated sessions. Please ensure that you are complying with applicable laws and regulations, including obtaining necessary end users permissions, prior to merging data sets.

overarching workflow and the basics of how it works
- applied to event dataset
- involves re-keying said event dataset
- adds a new column (stitched id)
- you can use this column in the new dataset in data views for a better deduplicated (or stitched) metrics and attribution

include example of actual stitching with tables n' stuff

prerequisites

supported stitching use cases, and future-supported stitching use cases
- analytics id + 1 column


call account manager and request stitching be enabled for a specific dataset
- what data they want to stitch
- what is the persistent id (exists on every row, such as analytics visitor ID but it doesn't have to be, we don't discriminate)
- what is the transient id (exists on some rows, such as logged in user or email or customer id)
- account manager does their magic and enables stitching for that dataset. respond with the stitched dataset and the field containing stitched id
- create or edit a connection and add the stitched dataset to the connection. choose the new stitched field as the person id.

spits out an ID map and stitched dataset
can't use the ID map and point it to another dataset

add disclaimer around GDPR
add disclaimer around customers giving consent

latency considerations?

1-month backfill by default

bring in replay.md? also weekly replay
