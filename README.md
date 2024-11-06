# assignments-S-M
Assignment for Software Modeling and Design Patterns


# Traffic Lights State Machine Diagram for Gishushu Road Junction

## Overview

This state machine diagram represents the control logic for traffic lights at Gishushu road junction. It depicts how traffic flows in multiple directions and how the traffic light system handles power outages or maintenance. The diagram ensures a smooth, sequential flow of green, yellow, and red lights for each direction, with clear transitions and timing.

## Diagram Structure

### Key Components

1. **Regions**: The diagram is divided into parallel regions representing each traffic flow direction:
   - **East-West Region: Kisimenti-Kimihurura**
   - **West-East Region: Kimihurura-Kisimenti**
   - **North-South Region: Nyarutarama-Gishushu** 

   Each region operates independently but has synchronization points to ensure the proper sequence of green, yellow, and red lights across all directions.

2. **States**: Each direction includes the following states:
   - **Green**: Traffic moves in the specified direction.
   - **Yellow**: A caution period before stopping traffic.
   - **Red**: Traffic stops to allow other directions to proceed.

3. **Transitions**: Each state transition has a specified timer to control the duration of the Green, Yellow, and Red states.

4. **Special States**:
   - **Idle (Power Off / Maintenance)**: Represents a state where the traffic lights are inactive due to power failure or maintenance.
   - **Final State**: Marks the end of one complete cycle. A transition from the Final State back to the Initial State ensures continuous looping.

### Traffic Light Sequence

The traffic lights sequence follows a specific order to allow safe flow through the junction. Here’s how each region operates:

1. **East to West (Kisimenti-Kimihurura)**:
   - **Green** for 45 seconds.
   - **Yellow** for 5 seconds, then turns **Red**.
   
2. **East to South(Kisimenti-Gishushu)** (runs in parallel with East to West):
   - **Green** for 10 seconds.
   - **Yellow** for 5 seconds, then turns **Red**, triggering the **West to East** flow.

3. **West to East(Kimihurura-Kisimenti)**:
   - **Green** for 45 seconds.
   - **Yellow** for 5 seconds, then turns **Red**.
   
4. **West to North(Kimihurura-Nyarutarama)** (runs in parallel with West to East):
   - **Green** for 10 seconds.
   - **Yellow** for 5 seconds, then turns **Red**.

5. **North to South and South to North (Nyarutarama to Gishushu)**:
   - After all other directions have completed their cycles, this direction turns **Green** for 20 seconds.
   - **Yellow** for 5 seconds, then turns **Red**.

This completes one full cycle, after which the sequence restarts.

### Handling Power Off or Maintenance

If the system needs to shut down (due to a power outage or scheduled maintenance or manually overriden by traffic police), it transitions to an **Idle** state. From the Idle state:
   - **Power Restored** or **Maintenance Complete** triggers a transition back to the Initial State, restarting the normal cycle.


## Usage Notes

- **Timers**: Timers control each transition, ensuring each state runs for a specified duration before switching.
- **Synchronization**: The diagram includes dependencies between certain regions to maintain traffic flow order, particularly between East to South and West to East, and West to North.
- **Repeating Cycle**: The system loops back to the Initial State after each cycle, enabling continuous operation.

## Conclusion

This state machine diagram provides a clear, structured flow for traffic lights at Gishushu junction, ensuring safe and coordinated movement of traffic in all directions. It also includes contingencies for power outages or maintenance, making the system resilient. 

--- 
