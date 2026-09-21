Delivery Robot State Model

System States (Task 2)
- IDLE: Robot is switched on and waiting for a delivery order at the warehouse base.
- NAVIGATING: Robot is moving along the planned path toward the destination coordinates.
- AVOIDING_OBSTACLE: Robot temporarily stops normal route navigation to steer around an obstacle.
- DELIVERING: Robot has reached the target location and is completing the package drop-off.
- RETURNING: Robot is traveling back to the warehouse base after delivery or due to low battery.

System Events and Conditions (Task 3)
- Delivery Request Received: Triggered when an order with destination coordinates is assigned.
- Obstacle Detected: Triggered when proximity sensors identify an obstacle in the navigation path.
- Obstacle Avoided: Condition met when path planning confirms clearance of the obstacle.
- Destination Reached: Spatial condition met when coordinates match the destination.
- Delivery Successful: Triggered when package handover is completed and confirmed.
- Critical Battery: Guard condition met when battery power drops below the critical threshold.
- Warehouse Reached: Spatial condition met when robot returns and docks at the warehouse base.

State Transitions
- IDLE -> NAVIGATING (on Delivery Request Received)
- NAVIGATING -> AVOIDING_OBSTACLE (on Obstacle Detected)
- AVOIDING_OBSTACLE -> NAVIGATING (on Obstacle Avoided)
- NAVIGATING -> DELIVERING (on Destination Reached)
- DELIVERING -> RETURNING (on Delivery Successful)
- NAVIGATING -> RETURNING (on Critical Battery)
- RETURNING -> IDLE (on Warehouse Reached)
