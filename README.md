# RPGFramework.Starter

Where a game on the RPG Framework begins: one package that installs the framework's modules and the packages they use,
and a sample that is a game's composition root, ready to change.

Requires Unity 6000.6 or newer. Installing it installs RPGFramework.Core, Field, Menu, Battle and the module router,
with their shared types, RPGFramework.Audio, RPGFramework.DI, RPGFramework.Localisation, the Input System and
Unity.Mathematics. The debug room is installed separately.

---

## Getting started

Import the **Starter** sample from the Package Manager and read its `README` first: like a new project from a template,
it needs a few steps of setup before Play — the Menu Sample and the 2D Field Sample imported, the menu's text installed,
the field exported, the Starter's input actions made the project's, and the scenes listed in the build. Then
`Entry Point` plays a splash screen and the title, and New Game begins in the sample field.

The sample is the game's side of the framework:

- **an entry point scene**, which builds the framework from the game's global installer and enters the first module;
- **a global installer** binding what the framework asks the game for — the localisation service, the music and SFX
  players, the transitions, the dialogue window, the variable map — and the stores the modules share;
- **module and scene databases**, naming each module's interface and scene;
- **a module router** deriving from `DefaultModuleRouter`;
- **the default settings, a variable map with every required variable, and input actions** with one action per control
  slot;
- **a splash screen module of its own**, showing how a game adds a module: an id, an interface, a module, the component
  binding it in its scene, and a route.

It plays no sounds: the music and SFX providers are empty and its audio intent player is silent, until a game gives them
sounds.
