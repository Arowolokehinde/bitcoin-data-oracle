# Weather Data Oracle Contract

## Overview
The Weather Data Oracle Contract is designed to handle IoT device registration, data submission, and reward distribution. It ensures data accuracy through consensus mechanisms and incentivizes participants with rewards.

## Constants
- `contract-owner`: The owner of the contract.
- `min-stake`: Minimum stake required for device registration (100 STX).
- `reward-per-submission`: Reward for each valid data submission (1 STX).
- `max-deviation`: Maximum allowed deviation for consensus (10%).
- `min-validators`: Minimum number of validators required for consensus (3).

## Error Codes
- `ERR-NOT-AUTHORIZED`: Error code 401, not authorized.
- `ERR-DEVICE-EXISTS`: Error code 402, device already exists.
- `ERR-INVALID-STAKE`: Error code 403, invalid stake amount.
- `ERR-DEVICE-NOT-FOUND`: Error code 404, device not found.
- `ERR-INVALID-DATA`: Error code 405, invalid data.
- `ERR-CONSENSUS-FAILED`: Error code 406, consensus failed.
- `ERR-LOW-ACCURACY`: Error code 407, low accuracy score.
- `ERR-INACTIVE-DEVICE`: Error code 408, inactive device.
- `ERR-INSUFFICIENT-STAKE`: Error code 409, insufficient stake.
- `ERR-INVALID-PROPOSAL`: Error code 410, invalid proposal.

## Data Structures
### Maps
- `device-index`: Maps device IDs to their respective owners.
- `device-owners`: Maps owners to their respective device IDs.
- `devices`: Stores device information including owner, stake, accuracy score, total submissions, and location.
- `weather-data`: Stores weather data submissions including temperature, humidity, pressure, wind speed, and validation status.
- `consensus-data`: Stores consensus data for weather measurements.
- `device-metrics`: Tracks device metrics such as last submission block, consecutive validations, total rewards, and total penalties.
- `proposals`: Stores governance proposals.
- `votes-cast`: Tracks votes cast on proposals.

### Data Variables
- `device-counter`: Counter for registered devices.
- `proposal-counter`: Counter for proposals.

## Public Functions
### Device Management
- `register-device`: Registers a new device with its location.
- `stake-device`: Stakes tokens for a registered device.
- `submit-data`: Submits weather data from a registered device.
- `validate-data`: Validates submitted data and distributes rewards.

### Quality Control
- `report-malfunction`: Reports a malfunctioning device and imposes penalties.
- `update-device-status`: Updates the status of a device based on activity.

### Governance
- `create-proposal`: Creates a new governance proposal.
- `vote-on-proposal`: Votes on an active proposal.

## Read-Only Functions
- `get-device-info`: Retrieves information about a specific device.
- `get-weather-data`: Retrieves weather data for a specific device and timestamp.
- `get-consensus-data`: Retrieves consensus data for a specific location and timestamp.
- `get-device-by-owner`: Retrieves the device ID owned by a specific owner.
- `get-owner-device`: Retrieves the device owned by a specific owner.

## Private Helper Functions
- `validate-measurement`: Validates a measurement against consensus data.
- `abs`: Calculates the absolute value of a number.

## Additional Constants
- `ACCURACY-THRESHOLD`: Minimum accuracy score (80).
- `PENALTY-AMOUNT`: Penalty amount for malfunctioning devices (10 STX).
- `MAX-INACTIVE-BLOCKS`: Maximum blocks without submission (1440).
- `GOVERNANCE-THRESHOLD`: Threshold for proposal passing (75%).

## Usage
1. **Register a Device**: Use `register-device` to register a new IoT device with its location.
2. **Stake Tokens**: Use `stake-device` to stake tokens for the registered device.
3. **Submit Data**: Use `submit-data` to submit weather data from the device.
4. **Validate Data**: Use `validate-data` to validate submitted data and distribute rewards.
5. **Governance**: Create and vote on proposals using `create-proposal` and `vote-on-proposal`.

## Conclusion
This contract ensures accurate weather data collection and incentivizes participants through a robust reward and penalty system. It also includes governance mechanisms for community-driven improvements.
