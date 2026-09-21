State Transition Table and Verification
State Transition Table (Task 4)

| Current State | Event / Condition | Next State | Action | Mapped Req. |
| :--- | :--- | :--- | :--- | :--- |
| IDLE | Delivery Request Received | NAVIGATING | Load coordinates and start moving | R1, R2 |
| NAVIGATING | Obstacle Detected | AVOIDING_OBSTACLE | Halt direct path, compute avoidance route | R3 |
| NAVIGATING | Critical Battery | RETURNING | Stop delivery journey, navigate to warehouse | R5 |
| NAVIGATING | Destination Reached | DELIVERING | Stop motion, initiate package delivery | R6 |
| AVOIDING_OBSTACLE | Obstacle Avoided | NAVIGATING | Resume navigation along original route | R4 |
| DELIVERING | Delivery Successful | RETURNING | Confirm delivery, navigate to warehouse | R7 |
| RETURNING | Warehouse Reached | IDLE | Dock at base, wait for next order | R8 |

Verification Activity (Task 5)
Check 1: Invalid Transition (IDLE -> DELIVERING)
- Can this happen?
No, this transition cannot happen.
- Explanation:
The robot cannot start delivering packages while sitting at the warehouse. It must first receive a delivery request and physically navigate to the destination coordinates. If this occurs, it directly violates Requirement R9 and R2.
Check 2: Missing Transition (NAVIGATING -> AVOIDING_OBSTACLE without return transition)
- What happens if there is no transition back? Can the robot continue its delivery?
No, the robot cannot continue its delivery.
- Explanation:
Without an outgoing transition back to NAVIGATING, the robot becomes permanently stuck in the AVOIDING_OBSTACLE state after clearing the object. This causes a deadlock or trap state where the mission is abandoned. That is why Requirement R4 is required to bring it back to normal navigation.
Check 3: Obstacle During Delivery (AVOIDING_OBSTACLE -> DELIVERING)
- Can the robot move from AVOIDING_OBSTACLE directly to DELIVERING?
No, this transition must not be allowed.
- Explanation:
An obstacle can appear at any point along the route. Jumping straight from obstacle avoidance into delivering would cause the robot to drop the package in the middle of transit instead of at the destination. The robot must return to NAVIGATING first and confirm arrival at the destination before delivering. This violates Requirement R10.
