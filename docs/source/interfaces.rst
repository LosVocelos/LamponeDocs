Lampone Interfaces
==================

This is the documentation for custom interfaces used for server-robot communication.
The interfaces are documented directly in the source code, but are also here to have all the documentation in one place.

Map message
-----------

.. code-block:: cpp

   # Size of the map in "pixels", other messages, like position of robots in map corresponds with these values.
   uint64 height
   uint64 width

   # Number of tiles in the map, how the map is segmented
   uint32 tiles_y
   uint32 tiles_x

   # Each element refers to one tile, which directions do roads go (length = tiles_y * tiles_x)
   # When converted to binary, it says which direction road goes and which does not, for example:
   #   0 (0b0000) - no road
   #   2 (0b0010) - east only (probably shouldn't happen)                  1. bit
   #   3 (0b0011) - north, east                                     4. bit  -|-   2.bit
   #  10 (0b1010) - west, east                                             3. bit
   uint8[] roads

TrafficLights message
---------------------

.. code-block:: cpp

   # How many Traffic Lights to set
   uint8 num

   # IDs of Traffic Lights to apply these settings (length = num)
   uint8[] ids

   # How the traffic lights are to be set (Always all lights together):
   # 0 (0b000) - no lights
   # 1 (0b001) - red
   # 2 (0b010) - yellow                                1. bit - red
   # 3 (0b011) - red, yellow                           2. bit - yellow
   # 4 (0b100) - green                                 3. bit - green
   uint8[] lights

TurnSignals message
-------------------

.. code-block:: cpp

   # Which Robot is sending the message
   string robot

   # Which turn signals are on (where the robot will go):
   # 0 - no signals
   # 1 - right                         <       >
   # 2 - left                        2. bit  1. bit
   # 3 - both
   uint8 blinkers

RegisterRobot service
---------------------

.. code-block:: cpp

   # Input - the name of the robot (for easy readiness)
   string name
   ---
   # returns unique id for every registered robot.
   int64 id
