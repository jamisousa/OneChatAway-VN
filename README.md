# ✦ One Chat Away - Visual Novel Project

<div align="center">

  <h3>A story-driven experience powered by a custom dialogue system.</h3>

  A Unity-based visual novel where every choice brings you closer to uncovering a mysterious character's true identity.

  <br/>

  <a href="https://github.com/jamisousa/unity-VN/releases/">
    <img src="https://img.shields.io/badge/▶_PLAY_THE_DEMO-8B5CF6?style=for-the-badge&logoColor=white" alt="Play the game"/>
  </a>
  <a href="https://github.com/jamisousa/unity-VN">
    <img src="https://img.shields.io/badge/EXPLORE_SOURCE-24212E?style=for-the-badge&logo=github&logoColor=white" alt="Explore source code"/>
  </a>

  <br/><br/>

  <img src="https://img.shields.io/badge/ENGINE-UNITY-8B5CF6?style=flat-square&logo=unity&logoColor=white" alt="Unity"/>
  <img src="https://img.shields.io/badge/LANGUAGE-C%23-C084FC?style=flat-square&logo=csharp&logoColor=white" alt="C sharp"/>
  <img src="https://img.shields.io/badge/GENRE-VISUAL_NOVEL-F9A8D4?style=flat-square" alt="Visual novel"/>

</div>

---

## ✧ Meet the Character

<div align="center">

  <img width="42%" alt="Visual novel character portrait — variation 1" src="https://github.com/user-attachments/assets/42d8ada9-39ad-427a-87d5-fb44a31bf520" />
  &nbsp;
  <img width="42%" alt="Visual novel character portrait — variation 2" src="https://github.com/user-attachments/assets/a60ef101-4bcb-414f-9cdf-2ef800d27e92" />

</div>

Engage through dialogue choices, explore his personality, and make decisions that shape the story as it unfolds!

**Will you take the time to get to know him and discover more?**

---

## 🎮 Playing the Demo

The game build is available on the releases page.

1. Download and extract the release ZIP file.
2. Open `VisualNovel.exe`.
3. Start playing!

<div align="center">

  <a href="https://github.com/jamisousa/unity-VN/releases/">
    <img src="https://img.shields.io/badge/DOWNLOAD_LATEST_RELEASE-8B5CF6?style=for-the-badge&logo=github&logoColor=white" alt="Download the game"/>
  </a>

</div>

---

## ✦ Game Features

<table>
  <tr>
    <td width="50%" valign="top">

### 💬 Dialogue & Story

- Interactive dialogue system with branching choices
- Input system for player interaction
- History logs displaying the most recent story text
- Auto reader and text skipping options
- Continue or stop skipping after choices

    </td>
    <td width="50%" valign="top">

### 🎭 Character System

- Character animations and expressions using sprite layers
- Configurable character creation
- Character positioning and display priority
- Sprite and color customization
- Animation playback and control

    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">

### 💾 Progression & Saves

- Save/load functionality
- Gallery system that unlocks images based on story progression
- Persistent variables through the Tag Manager

    </td>
    <td width="50%" valign="top">

### ⚙️ Settings & Accessibility

- Audio settings: music, ambience, SFX, and voice
- Resolution and fullscreen/windowed mode
- Auto-read and text-building speed settings
- Help menu with game controls

    </td>
  </tr>
</table>

---

## 🛠️ Extra Code Features

Beyond the visual novel itself, the project includes a customizable command system designed to make story scripting easier to extend and maintain.

| Feature | Description |
|:--|:--|
| **Text building** | Typewriter, fade, or instant text display |
| **Extensible commands** | Easily extendable commands to enhance your story |
| **Tag Manager** | Saves variables during the save/load process |

### Command Reference

<details>
<summary><strong>🕹️ General Commands</strong></summary>

| Command | Description |
|:--|:--|
| `Wait` | Waits for a command to finish before advancing to the next line of dialogue |
| `ShowUI` / `HideUI` | Show or hide the overall visual novel UI |
| `ShowDialogueBox` / `HideDialogueBox` | Show or hide the dialogue box |
| `Load` | Loads a new dialogue file, useful for story branches. Reads any `.txt` file, allowing the visual novel to load other `.txt` files from the `Resources` folder |

</details>

<details>
<summary><strong>🎭 Character Commands</strong></summary>

| Command | Description |
|:--|:--|
| `CreateCharacter` | Creates a character based on a `CharacterConfigSO` file |
| `MoveCharacter` | Moves a character to a specified position |
| `Show` / `Hide` | Show or hide characters |
| `SetPriority` | Displays a character on top of another |
| `SetPosition` | Changes the character's position |
| `SetColor` / `SetSprite` | Changes the character's appearance |
| `Animate` / `StopAnimation` | Runs or stops animations |

**Current animations:** `Hop` and `Shiver`

</details>

<details>
<summary><strong>🔊 Audio Commands</strong></summary>

| Command | Description |
|:--|:--|
| `PlaySFX` / `StopSFX` | Play or stop sound effects |
| `PlaySong` / `StopSong` | Play or stop music |
| `PlayAmbience` / `StopAmbience` | Play or stop ambient audio |

</details>

<details>
<summary><strong>🖼️ Graphic Panel Commands</strong></summary>

| Command | Description |
|:--|:--|
| `SetLayerMedia` | Changes layers of visual novel images, including background, foreground, cinematic, and others |
| `ClearLayerMedia` | Clears media displayed on a chosen layer |

</details>

<details>
<summary><strong>💗 Visual Novel Commands</strong></summary>

| Command | Description |
|:--|:--|
| `SetPlayerName` | Sets the player name based on the input on screen |
| `SetAffinity` | Sets affinity with the main character and updates hearts on screen |
| `HideCursor` | Hides the user's cursor. It does not actually stop the cursor from working, so story progression is not affected |
| `ShowCursor` | Shows the user's cursor |

</details>

<details>
<summary><strong>🖼️ Gallery Commands</strong></summary>

| Command | Description |
|:--|:--|
| `ShowGalleryImage` | Shows a gallery image and unlocks it in the gallery menu |
| `HideGalleryImage` | Hides a gallery image after it has been displayed |

</details>

> **For developers:** Refer to `CMD_DatabaseExtension_Examples` to create additional commands.

---

## 📚 Writing Your Own Story

If you'd like to clone this repository for reference or create your own project, keep the following in mind:

- Images and audio files are **not included** due to licensing restrictions.
- The story content and character sprites are **not included**, as they are my creations.
- To write and customize your own story, check the following files in `Assets/_Main`:
  - Character Configuration Asset
  - Dialogue System Configuration
  - Visual Novel Configuration
- To load character sprites, refer to `Assets/_TESTING/SpriteLoaderEditor.cs`.

The following examples demonstrate how to write story scripts using sprites, commands, player input, choices, and conditional branching.

### 1. Character Casting & Dialogue

This project supports character name casting, such as `'Your Name' as 'Something Else'`.

In the example below, `mainCharName` is a Tag Manager variable that will be saved to and retrieved from save files.

```text
SetLayerMedia(background YourBackgroundImage -l 0)
PlayAmbience(Rain -l true)
CreateCharacter(YourCharacterName)
wait(2)
YourCharacterName.Show()
YourCharacterName.Animate("Hop")
YourCharacterName.SetSprite(YourCharacterSpriteImage -l 0 -spd 1)
YourCharacterName as ??? "It's raining outside. The good kind of rain."
<mainCharName> "There's a good kind?"
YourCharacterName as ??? "Yeah. The soft one. The one that taps the window like it's checking in."
```

### 2. Player Input

In the example below, a panel will show up on screen for user input. `SetPlayerName` will populate the `mainCharName` variable. Saving and loading files will persist that value.

```text
input "What is your name?"
SetPlayerName(<input>)
```

### 3. Branching Choices

In the example below, a choice panel will appear on screen, and you can load new `.txt` files to continue the story based on user choices.

You can choose to enqueue text files or not, so it either waits for the current file to finish its lines or skips to the next file instead.

```text
YourCharacterName as ??? "Hey."
choice "Here you can add a title above the choices or keep it empty string"
{
    - "Who are you? And why am I here?"
        YourCharacterName.SetSprite(YourCharacterSpriteImage -l 0 -spd 1)
        YourCharacterName as ??? "Long story. Short answer: glitch."
        <mainCharName> as You "That... does not help."
        SetAffinity(+1)

    - "Okay, then just send me back."
        YourCharacterName.SetSprite(YourCharacterSpriteImage -l 0 -spd 1)
        YourCharacterName as ??? "I would if I could."
        <mainCharName> as You "That is extremely reassuring."
        SetAffinity(0)
}
```

### 4. Conditional Dialogue & Chapter Loading

Using the example below, you can customize your story based on variables and comparisons.

In this case, if the affinity with the main character is greater than `2`, the good route will load; otherwise, the neutral route will load.

```text
narrator "Something about this moment feels important."
if(<affinity> > 2)
{
    YourCharacterName as ??? "I like you... I think. Just a little."
    Load(Chapter_G1 -enqueue false)
}
else
{
    Load(Chapter_N1 -enqueue true)
}
```

---

## ✦ Game Showcase

<div align="center">

  <p><em>A closer look into the world, interface, and interactive storytelling of this visual novel.</em></p>

  <br/>

  <img width="100%" alt="Gameplay showcase — main scene" src="https://github.com/user-attachments/assets/a562a371-a6b0-4aeb-aae5-8ecba1811a73" />

  <br/><br/>

  <table>
    <tr>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 2" src="https://github.com/user-attachments/assets/4909a4c4-ff7d-4e35-9a73-e998bf6cf27c" />
      </td>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 3" src="https://github.com/user-attachments/assets/38c58a66-f6e8-4d64-8142-bb36c15aa271" />
      </td>
    </tr>
    <tr>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 4" src="https://github.com/user-attachments/assets/12ff5e0a-d716-4d5d-bb52-f9dfbeec7764" />
      </td>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 5" src="https://github.com/user-attachments/assets/940d32c8-2fe2-4edd-9662-42276aab24a0" />
      </td>
    </tr>
    <tr>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 6" src="https://github.com/user-attachments/assets/20e83af7-1afb-4382-afe8-966aa83d702d" />
      </td>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 7" src="https://github.com/user-attachments/assets/f1751285-6cf0-4f6f-996f-918811e348cb" />
      </td>
    </tr>
    <tr>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 8" src="https://github.com/user-attachments/assets/5f82bc72-6692-44e7-8ce8-8b26232fe35f" />
      </td>
      <td align="center" width="50%">
        <img width="100%" alt="Gameplay showcase — scene 9" src="https://github.com/user-attachments/assets/5d5c7a4b-3fb1-419e-af5c-5d1b4f7b47d0" />
      </td>
    </tr>
  </table>

  <br/>

  <img width="100%" alt="Gameplay showcase — final scene" src="https://github.com/user-attachments/assets/59e7f547-c58f-4f40-9aa1-e36e7b91a7f0" />

  <br/><br/>

  <a href="https://github.com/jamisousa/unity-VN/releases/">
    <img src="https://img.shields.io/badge/EXPERIENCE_THE_DEMO-8B5CF6?style=for-the-badge&logo=unity&logoColor=white" alt="Experience the demo"/>
  </a>

</div>

---

## 💜 Acknowledgments

A huge thanks to [Stellar Studio](https://www.youtube.com/@stellarstudio5495) for making an incredible, free [course](https://www.youtube.com/watch?v=cO6NzrvTrkY&list=PLGSox0FgA5B58Ki4t4VqAPDycEpmkBd0i) available to everyone on YouTube. His lessons were essential to creating this project.

---

## 📖 Resource Credits

Credits for each image, video, and sound used in the game can be found in `ResourcesCredits.md`.

Please refer to the [respective file](https://github.com/jamisousa/unity-VN/blob/refactor/cleanup/ResourcesCredits.md) for full attribution details and original sources.

---

<div align="center">

  <sub>Built with Unity and C# </sub>

</div>
