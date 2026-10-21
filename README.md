# Echoes of Bathala: Unity Client Demo

**Demo loop:** Choose class + name → spawn → navigate → talk to quest giver → kill common monsters → collect Perlas → talk to quest giver → convert Perlas to Baku at the forge.

---

## Dev Guide

### 1. Requirements

- **Unity version:** `6000.6.7f1` (lts)
- [Git](https://git-scm.com/) and [Git LFS](https://git-lfs.com/)

### 2. Clone the repo

```bash
git lfs install        # once per machine, do this BEFORE cloning
git clone https://github.com/coderold/EOB-Client.git
cd EOB_Client
```

Then open the folder in Unity Hub with the version above and let it finish importing (the first open takes a while).

> If models or textures show up as tiny text files or pink/broken, LFS was not installed before cloning. Run `git lfs install` then `git lfs pull`.

### 3. Folder structure

```
Assets/
├── Scripts/
│   ├── Core/            EventBus, PlayerSession, Stats, Health, IInteractable
│   ├── Player/          Controller, camera, input, death/respawn
│   ├── Combat/          SkillCaster, SkillDefinition, ClassDefinition, targeting
│   ├── Monsters/        MonsterAI, MonsterDefinition, Spawner
│   ├── Items/           ItemDefinition, LootTable, ItemPickup, Wallet
│   ├── Quests/          QuestDefinition, QuestManager, Dialog, QuestGiverNpc
│   ├── Forge/           BakuForge, IForgeService, LocalForgeService
│   └── UI/              HUD, Dialog, Forge, CharacterCreation
├── Data/                ScriptableObject assets (classes, skills, monsters, items, quests, dialogs)
├── Prefabs/
├── Art/                 models, animations, materials, icons
├── Scenes/              CharacterCreation, World, Sandbox_<name>
└── ThirdParty/          untouched imported packs
```

**Assets**
- Free assets only (Mixamo, Unity Asset Store, etc.).
- Put imported packs in `ThirdParty/` and don't edit them. Copy what you need into `Art/` or `Prefabs/`.
- Import only what you use. LFS storage and bandwidth are limited, so delete unused demo scenes and textures.
