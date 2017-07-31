# Ambient sound

## Synopsis

Background sounds for focusing or create a relaxing ambiance.

## Installation

Install the neuron into your resource directory
```bash
kalliope install --git-url https://github.com/kalliope-project/kalliope_neuron_ambient_sound.git
```

## Options

| parameter    | required | type   | default          | choices             | comment                                                                     |
|--------------|----------|--------|------------------|---------------------|-----------------------------------------------------------------------------|
| state        | YES      | string |                  | "on", "off"         | Target state of the ambient sound.                                          |
| sound_name   | NO       | string |                  | See the list bellow | If not set, a sound will be selected randomly                               |
| mplayer_path | NO       | string | /usr/bin/mplayer |                     | Path to mplayer binary. By default /usr/bin/mplayer on Debian family system |

List of available sound:
- birds
- fireplace
- forest
- forest-rain
- forest-stream
- heavy-rain
- mountain-steam
- ocean-waves
- seaside
- stream
- summer-rain
- thunderstorm
- tropical-beach
- tropical-thunderstorm
- urban-thunderstorm
- wind
- wood-sailboat


## Return Values

| Name          | Description              | Type   | sample    |
|---------------|--------------------------|--------|-----------|
| playing_sound | The current sound played | string | fireplace |

## Synapses example

Start an ambient sound randomly
```yml
- name: "ambient-random"
  signals:
    - order: "ambient sound"
  neurons:
    - ambient_sound:
        state: "on"
```

```yml
- name: "ambient-stop"
  signals:
    - order: "stop ambient sound"
  neurons:
    - ambient_sound:
        state: "off"
```

Play selected ambient sound
```yml
- name: "ambient-random"
  signals:
    - order: "ambient sound"
  neurons:
    - ambient_sound:
        state: "on"
        sound_name: "forest-rain"
```

## Notes

You add your own sound file inside the "sound" folder.

## Licence

MIT
