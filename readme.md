# FRED Dataset Classification

Classification for each of the FRED datasets, with tags denoting relevant 
information about each one.

## Format

Tags are in the CSV file. Each row is a dataset, ordered like this:

```
number, train/test, tags, ...
```

Each dataset will have a tag for the number of drones in it (1-drone, 2-drones,
etc.) and tags for any relevant obstructions (ie none, rain, darkness, etc.)

## Tag glossary

Here's a list of all the tags I've used, with definitions.

**Number of drones:**

- `1-drone`
- `2-drones`

All videos contain exactly one of these tags.

**Location of footage:**

- `outside`
- `inside`

All videos contain exactly one of these tags.

**Obstructions:**

- `no-obstructions`: No major obstructions. Video might contain small pockets of
noise from bugs flying around, wind blowing grass, light changes, etc.
- `far-away`: The drone is far enough away for a significant portion of the 
video, making it difficult to discern
- `birds`: One or more birds fly such that they could be mistaken for a drone
- `dark`: There's not enough light for the drone to be visible in the RGB 
footage. This is significant because it means the drone produces a more 
noticable event trail than it otherwise would
- `bugs`: A significant amount of noise is created by bugs and other small 
flying critters, such that the drone can be lost in the noise. Note that not 
every video containing bugs is tagged, only those where the bugs produce
significant noise
- `lens-flare`: There's a light source bright enough to cause lens flare,
distoring the image and making the drone events harder to spot
- `drone-shadow`: Drone produces a shadow which could easily be mistaken as the drone itself.
- `overlap`: Drone overlaps with another moving thing (tree, person, etc), making its events difficult to separate from the other thing.
- `drone-dies`: Drone is consecutively not present for at least half of the vidoe, usually due to dying or running into something. Also includes videos where the drone does not make an appearance for much of the video.
- `rain`: It is raining in the video.
- `bump`: A large amount of noise is caused by the drone operators bumping the 
camera.
- `vehicles`: A significant amount of noise is created by vehicles in the
background.

All videos contain at least one of these tags. Videos tagged with 
`no-obstructions` will have no other tags.
