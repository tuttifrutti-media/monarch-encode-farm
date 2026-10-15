# monarch-encode-farm
Segment encode workers for TuttiFrutti video builds. Dispatch `encode-segment`
with the master's Drive part URLs (in order), its sha256, and the segment grid
(start/duration) from the local segmented-encode script. Each job reassembles
the master, verifies the hash, encodes one segment with the FB 720p profile,
and returns it as an artifact. Local verification (ffprobe duration gate +
concat assertion) remains the acceptance step — farm output is never trusted
unverified.
