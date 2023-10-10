# Build Instructions
> [!WARNING]  
> This is all still in Beta development. Things will change. You need to have a good understanding of Klicky (+macro settings), probes, offsets and Klipper.

> [!IMPORTANT]  
> Klicky-00 is a Loooong probe. It doesn't fit behind the print bed of a standard Voron 2.4 or Trident build without a dock that retracts the probe. See "Bump dock" instructions below.

> [!WARNING]  
> You need at least 5mm travel on Y past the back of your build plate for this to work.

## Klicky-00 Probe
The probe is built from components of other projects. The original concept of this project is putting the probe under the nozzle in a repeatable/automatable way.

### BOM (PCB_Klicky Version)
| Qty | Item                 | Note                                                                                                    |
| --- | -------------------- | ------------------------------------------------------------------------------------------------------- |
| 1   | PCB Klicky Lower kit | Lower PCB with switch removed, magnets, screws and heatset inserts that came with the kit or equivalent |
| 5   | 6x3mm Disc Magnets   | Probably a mix of N52 and N35 strength for adjustability                                                |
| 4   | M2.5 x 20mm SHCS     | Swing arm hinges                                                                                        |
| 2   | Lengths of wire      | Less than 2mm sheathing diameter, approx 100mm                                                          |
| 1   | M3 x 12mm SHCS       | Unklicky probe stylus retention screw                                                                   |

### BOM (Standard Klicky Version [Assumes you already have the Klicky mount on your toolhead])
| Qty | Item                                      | Note                                                     |
| --- | ----------------------------------------- | -------------------------------------------------------- |
| 8   | 6x3mm Disc Magnets                        | Probably a mix of N52 and N35 strength for adjustability |
| 4   | M2.5 x 20mm SHCS                          | Swing arm hinges                                         |
| 2   | Lengths of wire                           | Less than 2mm sheathing diameter, approx 100mm           |
| 2   | M2 x 10mm self tapping countersunk screws |                                                          |
| 1   | D2F switch                                | No lever                                                 |

### Printed Parts
| Probe Body/Switch (pick 1)                                             | Swingarms (pick 1)                                                           | Rear Body (pick 1)                                    |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------- |
| Unklicky: [Standard](STL/Klicky-00-Probe_Body-Unklicky.stl)            | Xol-Toolhead: [PCB_Klicky](STL/Klicky-00-swingarms-Xol-PCB_Klicky.stl)       | [PCB_Klicky](STL/Klicky-00-Rear_Body-PCB_Klicky.stl)  |
| D2F: [Standard](STL/Klicky-00-Probe_Body-D2F.stl)                      | Xol-Toolhead: [Standard Klicky](STL/Klicky-00-swingarms-Xol-Klicky.stl)      | [Standard Klicky](STL/Klicky-00-Rear_Body-Klicky.stl) |
| Unklicky: [Archetype](STL/Klicky-00-Probe_Body-Archetype-Unklicky.stl) | Archetype: [PCB_Klicky](STL/Klicky-00-swingarms-Archetype-PCB_Klicky.stl)    |                                                       |
| D2F: [Archetype](STL/Klicky-00-Probe_Body-Archetype-D2F.stl)           | StealthBurner: [Fits both Klicky types](STL/Klicky-00-swingarms-SB-both.stl) | [StealthBuner Probe Mount (Centered)](STL/Klicky-00_AB-SB_mount_centered.stl)                                                      |
| Unklicky: [StealthBurner](STL/Klicky-00-Probe_Body-SB-Unklicky.stl)    |                                                                              |                                                       |
| D2F: [StealthBurner](STL/Klicky-00-Probe_Body-SB-D2F.stl)              |                                                                              |                                                       |

### Instructions (PCB_Klicky Version)
| Note                                                                                                                                                                                                                                                                                                                      | Picture                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| Remove the built in support                                                                                                                                                                                                                                                                                               | ![Alt text](images/probe_remove_support.png)      |
| Install the M2 heatset inserts                                                                                                                                                                                                                                                                                            | ![Alt text](images/probe_install_heatsets.png)    |
| Drill out the swing arm holes with M2.5 drill bit                                                                                                                                                                                                                                                                         | ![Alt text](images/probe_drill_arms.png)          |
| Prepare the probe stylus. Sand it down so it moves smoothly inside the probe front body                                                                                                                                                                                                                                   | ![Alt text](images/probe_prepare_stylus.png)      |
| Install the stylus as per UnKlickyBFP. Wire wraps around top of stylus, Magnets are opposing <br/> `*TIP: Make sure that the top magnet repells the furthest back magnet on the toolhead. This will make sure that Klicky-00 is pushed down as the toolhead moves over it to attach the probe.`                                                                                                                                                                                                                             | ![Alt text](images/probe_install_stylus.png)      |
| Put the screw in most of the way. Leave room for the second wire to wrap around                                                                                                                                                                                                                                           | ![Alt text](images/probe_install_stylus2.png)     |
| Put the left side wire in place, wrapped around the screw and tighten the screw                                                                                                                                                                                                                                           | ![Alt text](images/probe_wire_left.png)           |
| Install the front two swing arm screw hinges                                                                                                                                                                                                                                                                              | ![Alt text](images/probe_attach_arms1.png)        |
| Install a magnet in the back of the lower swing arm                                                                                                                                                                                                                                                                       | ![Alt text](images/probe_lower_arm_magnet.png)    |
| Install the other two swing arm screws                                                                                                                                                                                                                                                                                    | ![Alt text](images/probe_attach_arms2.png)        |
| Solder the probe wires to the bottom of the PCB Klicky lower PCB. One in the front, one at the back. Middle hole stays empty                                                                                                                                                                                              | ![Alt text](images/probe_solder_wires.png)        |
| Install the magnets that live under the PCB. The rear one should attract to the dock, the other should repel the lower swing arm. You may need to swap between N35 and N52 magnets to get just enough spring force to activate the swing arm. Too much won't let the arm move and will push the klicky PCB magnets apart. | ![Alt text](images/probe_rear_body_magnets.png)   |
| Install the Klicky PCB magnets with the counter sunk screws. Get your polarity right.                                                                                                                                                                                                                                     | ![Alt text](images/probe_install_pcb_magnets.png) |

### Instructions (Stanrad Klicky Version)
[Todo (sorry)]

## Bump dock
![Alt text](images/bump_dock.png)
In the spirit of Unklikcy, this atrocity is put together out of things that hopefully you have laying around as spare parts.

Like the rest of Klicky-00, magnets are used as "springs" because they're magic.

### BOM
| Qty     | Item              | Note                                                                  |
| ------- | ----------------- | --------------------------------------------------------------------- |
| 2       | M5 x 16 BHCS      | Attaching to gantry                                                   |
| 2       | M5 T-Nuts         | Attaching to gantry                                                   |
| 1       | M3 Heatset Insert | Standard Voron spec. In the height adjuster-a-thingy                  |
| 1       | M3 x 30 SHCS      | Height adjustment screw                                               |
| 2       | M3 Heatset Insert | Standard Voron spec. In the front of the klicky dock hoder            |
| 2       | 36mm PTFE Tube    | 2mm ID / 4mm OD PTFE Tube: lower hinges                               |
| 4       | 40mm PTFE Tube    | 2mm ID / 4mm OD PTFE Tube: Middle hinges + Bump slide                 |
| 2       | 30mm PTFE Tube    | 2mm ID / 4mm OD PTFE Tube: Upper hinges                               |
| 5 or 10 | 6x3mm Magnets     | Depending on how strong the magnets are: the "Springs" for the bumber |
| 2       | M3x20 SHCS        | Klicky dock to bump dock                                              |
| 1       | 6x3mm Magnet      | Behind Klicky dock                                                    |

### Instructions
| Note                                                                                                                                                                                                                                                                                                               | Picture                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| Install heatset inserts: <br/> * Lower arm and height adjuster                                                                                                                                                                                                                                                     | ![Alt text](images/bump_dock_heatsets.png)   <br/>  ![Alt text](images/bump_dock_height_adj_heatset.png) |
| Put the dock arms together with the PTFE tube in the upper and lower hinges. Don't forget the other PTFE tube on the front of the bumper!                                                                                                                                                                          | ![Alt text](images/bump_dock_assemble_arms.png)                                                          |
| Slide the arms into place in the body and put the two middle hinge PTFE tubes in place                                                                                                                                                                                                                             | ![Alt text](images/bump_dock_assemble_dock.png)                                                          |
| Thread the height adjustment screw into the height adjuster and clip it into place                                                                                                                                                                                                                                 | ![Alt text](images/bump_dock_height_adj.png)                                                             |
| Attach the Klicky dock to the bump dock. Don't forget the magnet and it's polarity if you have existing probes                                                                                                                                                                                                     | ![Alt text](images/bump_dock_klicky-dock.png)                                                            |
| Install Magnets to be the "springs" and "latch" <br/><br/> Depending on how strong your magnets are, and how well everything moves, you may only need these magnets on one side. The top three magnets are setup to push the upper arm forward and the lower two magnets attract to pull the lower part backwards. | ![Alt text](images/bump_dock_springs.png)                                                                |
| Time to install it into the printer.                                                                                                                                                                                                                                                                               | ![Alt text](images/bump_dock_into_printer.png)                                                           |
