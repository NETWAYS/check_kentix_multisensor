check_kentix_multisensor
========================

Checks the status of Kentix MultiSensor-LAN devices.

### Requirements

* Python libraries: `pysnmp`, `nagaconda` (shipped)


### Usage

    # ./check_kentix_multisensor -h HOST [-s COMMUNITY] [-t THRESHOLDS] [-w WARNING] [-c CRITICAL]

Example:

    ./check_kentix_multisensor -h <host>
        -w temperature=~:25 \
        -c temperature=~:30
    
    This check would be CRITICAL if one of the following conditions are met:
    -The check request fails (wrong IP address, device unavailable, etc.).
    -The sensor's temperature value is above 30.
    
    The check would return a WARNING if the temperature value is above 25 unless
    one of the CRITICAL conditions were encountered - in which case
    the CRITICAL condition takes precedence.
    
    Instead of manually specifying warning/critical ranges you can use the -t 1
    option to use the alarm settings you configured in the device's web interface.


