

## [v1.0.1] - 2025-05-04
### Fixed
- Resolved all `!input` issues inside Jinja templates in blueprint
- Replaced invalid `numeric_state` trigger with `template` trigger using resolved variables
- Finalized safe usage of pause, moisture_low, and moisture_high using intermediate entity references
- Blueprint now imports and runs cleanly in Home Assistant
