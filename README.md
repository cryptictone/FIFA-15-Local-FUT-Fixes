# FIFA-15-Local-FUT-Fixes
# FIFA 15 Local FUT Fixes

Fixes for the FIFA 15 Local FUT public test build.

## Fixes

### Origin / LSX disconnect during matches
Prevents an idle LSX socket timeout from being treated as an Origin disconnect.

This fixes the message:

"This is a result of the Origin Client being terminated"

during longer matches.

### Offline Seasons / Divisions crash
Fixes an invalid Offline Seasons response where FIFA could receive an active
season without the SeasonData/progressData required to resume it.

The server now returns the fresh/inactive descriptor when no resumable season
data exists.

## Tested

Tested through the full Offline Seasons flow:

- Entered Offline Seasons successfully
- Started and completed a full match
- No Origin/LSX shutdown during gameplay
- Match result submitted successfully
- Match coins awarded
- Season record and points updated
- Returned to Offline Seasons successfully
- Subsequent season match completed successfully

## Installation

1. Back up your existing `localfut15/server.py`.
2. Replace it with the `server.py` from this repository.
3. Restart the Local FUT server.
4. Launch FIFA 15 normally.

Made for the FIFA 15 Local FUT public test build.
