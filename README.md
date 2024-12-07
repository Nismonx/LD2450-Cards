# LD2450-Cards
LD2450 custom cards to ease mm-wave sensor setting up.

This is primarily aim to work with HACS custom integration by MassiPi [LD2450 porject](https://github.com/MassiPi/ld2450_ble/tree/main) who has ported the official Hi-Link-LD2410-over-Bluetooth integration onto LD2450. [LD2410 project](https://www.home-assistant.io/integrations/ld2410_ble/)

It is required to update the firmware of the LD2450 to the latest, this can be done via the HLKRadartool available in the Play Store. 

My module came with an external ble antena and the range is very decent. 
Despite the previous statement, I would still recommend using a Bluetooth proxy mainly if there's more than one ble devices in HA.


 
# The following code requires installation of the Plotly Graph Card from HACS in Home Assistant.

To use this card, add the custom HACS integration [Plotly Graph](https://my.home-assistant.io/redirect/hacs_repository/?repository=lovelace-plotly-graph-card&owner=dbuezas&category=Plugin)


```shell
type: custom:plotly-graph
refresh_interval: 1
hours_to_show: current_day
ha_theme: true
layout:
  legend:
    "y": 100
    orientation: h
  height: 330
  margin:
    l: 30
    r: 20
    t: 10
    b: 30
  showlegend: true
  xaxis:
    dtick: 100
    gridcolor: RGBA(200,200,200,0.15)
    zerolinecolor: RGBA(200,200,200,0.15)
    type: number
    fixedrange: true
    range:
      - 400
      - -400
  yaxis:
    dtick: 100
    gridcolor: RGBA(200,200,200,0.15)
    zerolinecolor: RGBA(200,200,200,0.15)
    scaleanchor: x
    scaleratio: 1
    fixedrange: true
    range:
      - 600
      - 0
entities:
  - entity: ""
    name: Person1
    show_value: true
    unit_of_measurement: cm
    marker:
      size: 12
    line:
      shape: spline
      width: 5
    x:
      - $ex hass.states["sensor.hlk_ld2450_ca2d_target_one_x"].state /-10
    "y":
      - $ex hass.states["sensor.hlk_ld2450_ca2d_target_one_y"].state /10
  - entity: ""
    name: Person2
    show_value: true
    unit_of_measurement: cm
    marker:
      size: 12
    line:
      shape: spline
      width: 5
    x:
      - $ex hass.states["sensor.hlk_ld2450_ca2d_target_two_x"].state /-10
    "y":
      - $ex hass.states["sensor.hlk_ld2450_ca2d_target_two_y"].state /10
  - entity: ""
    name: Person3
    show_value: true
    unit_of_measurement: cm
    marker:
      size: 12
    line:
      shape: spline
      width: 5
    x:
      - $ex hass.states["sensor.hlk_ld2450_ca2d_target_three_x"].state /-10
    "y":
      - $ex hass.states["sensor.hlk_ld2450_ca2d_target_three_y"].state /10
  - entity: ""
    name: Zone1
    mode: lines
    fill: toself
    fillcolor: RGBA(20,200,0,0.1)
    line:
      color: RGBA(20,200,0,0.2)
      shape: line
      width: 2
    x:
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_first_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_first_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_second_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_second_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_first_vertex_x"].state
        /-10
    "y":
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_first_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_second_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_second_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_first_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_one_first_vertex_y"].state
        /10
  - entity: ""
    name: Zone2
    mode: lines
    fill: toself
    fillcolor: RGBA(200,0,255,0.1)
    line:
      color: RGBA(200,0,255,0.2)
      shape: line
      width: 2
    x:
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_first_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_first_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_second_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_second_vertex_x"].state
        /-10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_first_vertex_x"].state
        /-10
    "y":
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_first_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_second_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_second_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_first_vertex_y"].state
        /10
      - >-
        $ex hass.states["number.hlk_ld2450_ca2d_area_two_first_vertex_y"].state
        /10
  - entity: ""
    name: Zone3
    mode: lines
    fill: toself
    fillcolor: RGBA(200,120,55,0.1)
    line:
      color: RGBA(200,120,55,0.2)
      shape: line
      width: 2
    x:
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_first_vertex_x"].state
        /-10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_first_vertex_x"].state
        /-10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_second_vertex_x"].state
        /-10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_second_vertex_x"].state
        /-10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_first_vertex_x"].state
        /-10
    "y":
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_first_vertex_y"].state
        /10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_second_vertex_y"].state
        /10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_second_vertex_y"].state
        /10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_first_vertex_y"].state
        /10
      - >-
        $ex
        hass.states["number.hlk_ld2450_ca2d_area_three_first_vertex_y"].state
        /10
  - entity: ""
    name: Coverage
    mode: lines
    fill: null
    fillcolor: rgba(168, 216, 234, 0.15)
    line:
      shape: line
      width: 1
      color: rgba(100, 100, 100, .6)
      dash: dot
    x:
      - 0
      - $ex 600 * Math.sin((2 * Math.PI)/360 * 60)
      - 450
      - 400
      - 300
      - 200
      - 100
      - 0
      - -100
      - -200
      - -300
      - -400
      - -450
      - $ex -600 * Math.sin((2 * Math.PI)/360 * 60)
      - 0
    "y":
      - 0
      - $ex 600 * Math.cos((2 * Math.PI)/360 * 60)
      - $ex Math.sqrt( 600**2 - 450**2 )
      - $ex Math.sqrt( 600**2 - 400**2 )
      - $ex Math.sqrt( 600**2 - 300**2 )
      - $ex Math.sqrt( 600**2 - 200**2 )
      - $ex Math.sqrt( 600**2 - 100**2 )
      - 600
      - $ex Math.sqrt( 600**2 - 100**2 )
      - $ex Math.sqrt( 600**2 - 200**2 )
      - $ex Math.sqrt( 600**2 - 300**2 )
      - $ex Math.sqrt( 600**2 - 400**2 )
      - $ex Math.sqrt( 600**2 - 450**2 )
      - $ex 600 * Math.cos((2 * Math.PI)/360 * 60)
      - 0
raw_plotly_config: true
cards:
  - type: heading
    heading: Office - LD2450

```
To use this card, replace the sensor names with your sensor's name.

For example:
"sensor.hlk_ld2450_ca2d_"

Replace "ca2d" with the mac address of your device

# brief explanation on how zones work:

https://github.com/lazarbankovic/hilink-ld2450/blob/main/include/Ld2450.h#L119-L140
