# Endless Velocity - Module Architecture Design

## 🏗️ **Modular Design Philosophy**

The Endless Velocity project uses a **layered modular architecture** where each module has a specific, non-overlapping purpose. This ensures maximum compatibility and user choice.

## 📦 **Module Hierarchy & Dependencies**

```
┌─────────────────────────────────────────┐
│           OVERHAUL MODULE               │
│    (Galaxy Structure & Missions)       │
│                                         │
│  ┌─────────────────┐ ┌─────────────────┐│
│  │  EV NOVA MODULE │ │  ARPIA2 MODULE  ││
│  │ (Ships & Factions) │ (Arpian Content) ││
│  └─────────────────┘ └─────────────────┘│
└─────────────────────────────────────────┘
            │
            ▼
    ┌─────────────────┐
    │  ENDLESS SKY    │
    │   (Base Game)   │
    └─────────────────┘
```

## 🎯 **Module Responsibilities**

### **EV Nova Module** ✅ COMPLETE
**Purpose**: Add EV Nova content to existing Endless Sky universe
- ✅ **Ships**: All 60 EV Nova ships (Federation, Auroran, Polaris, Vell-os, Pirates, Rebels, Civilians)
- ✅ **Outfits**: 34 unique EV Nova technologies (Jump Drives, Cloaking, Bio-tech, etc.)
- ✅ **Governments**: All EV Nova factions with proper relationships
- ✅ **Fleets**: Battle groups and patrol compositions for all factions
- **Integration**: Works alongside existing ES content
- **Dependencies**: Only base Endless Sky
- **Conflicts**: None (designed for compatibility)

### **Arpia2 Module** 🔧 IN DEVELOPMENT
**Purpose**: Add Arpia 2 plugin content to existing universe
- 🔧 **Ships**: Arpian vessels and hybrid technology
- 🔧 **Storylines**: Three parallel exploration/trade/protection storylines
- 🔧 **Factions**: Arpian civilization and related groups
- 🔧 **Systems**: Deep space regions and Arpian territories
- **Integration**: Works with or without EV Nova Module
- **Dependencies**: Only base Endless Sky
- **Conflicts**: None

### **Overhaul Module** 📋 NEEDS IMPLEMENTATION
**Purpose**: Transform galaxy structure for complete EV Nova experience
- **Systems**: Replace ES galaxy with EV Nova star map
- **Planets**: EV Nova worlds, stations, and spaceports
- **Missions**: Core EV Nova storylines and side missions
- **Galaxy Structure**: Hyperspace routes matching EV Nova
- **Starting Conditions**: EV Nova starting scenario
- **Integration**: **REQUIRES** both EV Nova and Arpia2 modules
- **Dependencies**: EV Nova Module + Arpia2 Module + base game
- **Conflicts**: None with required modules

## 🔧 **Fixed Architecture Issues**

### **Problem Identified** ❌
The original design had a **circular dependency conflict**:
- EV Nova Module declared `conflicts "Overhaul Module"`
- Overhaul Module declared `requires "EV Nova Module"`
- This made it impossible to use both modules together!

### **Solution Implemented** ✅
1. **Removed Conflicts**: EV Nova Module no longer conflicts with anything
2. **Clear Dependencies**: Overhaul Module properly requires both content modules
3. **Separation of Concerns**: Each module has distinct, non-overlapping content
4. **Layered Architecture**: Higher modules build upon lower modules without duplication

## 📊 **Module Combinations & User Experience**

| Modules Installed | Result | Experience Type |
|-------------------|--------|-----------------|
| **EV Nova only** | EV Nova factions added to ES galaxy | Enhanced Endless Sky |
| **Arpia2 only** | Arpian content added to ES galaxy | Story-focused addition |
| **EV Nova + Arpia2** | Both faction sets in ES galaxy | Rich content expansion |
| **All three modules** | Complete EV Nova universe | Full EV Nova conversion |

## 🎯 **What Each Module Should NOT Contain**

### **EV Nova Module** (Content Provider)
- ❌ **No galaxy structure changes** (that's Overhaul's job)
- ❌ **No system replacements** (works within existing ES galaxy)
- ❌ **No starting scenario changes** (preserves ES experience)

### **Arpia2 Module** (Content Provider)
- ❌ **No EV Nova ships/outfits** (that's EV Nova Module's job)
- ❌ **No galaxy overhaul** (that's Overhaul's job)
- ❌ **No duplicate content** (unique Arpian material only)

### **Overhaul Module** (Coordinator)
- ❌ **No ships or outfits** (uses content from other modules)
- ❌ **No faction definitions** (uses governments from other modules)
- ❌ **No fleet compositions** (uses fleets from other modules)

## 🏆 **Benefits of This Architecture**

### **Maximum User Choice**
- Users can install any combination they want
- Each module provides value independently
- Progressive enhancement from basic addition to total conversion

### **No Conflicts**
- Each module has distinct responsibilities
- No overlapping or duplicate content
- Clean dependency chain without circular references

### **Easy Maintenance**
- Changes to ships/outfits only affect EV Nova Module
- Galaxy structure changes only affect Overhaul Module
- Clear separation makes debugging easier

### **Asset Efficiency**
- Ships and outfits assets created once in EV Nova Module
- Overhaul Module reuses existing assets
- No duplicate asset creation needed

## 🚀 **Implementation Status**

### **EV Nova Module** ✅ **100% COMPLETE**
- All ships, outfits, governments, and fleets implemented
- Fully integrated with Endless Sky systems
- Ready for asset creation

### **Arpia2 Module** 📋 **NEEDS DEVELOPMENT**
- Basic structure exists
- Content implementation needed
- Storylines and missions to be added

### **Overhaul Module** 📋 **NEEDS IMPLEMENTATION**
- Plugin structure fixed
- Galaxy map replacement needed
- EV Nova systems and planets to be added
- Starting scenario configuration needed
- Mission storylines to be implemented

## 🎯 **Next Steps**

1. **Complete Arpia2 Module** content implementation
2. **Implement Overhaul Module** galaxy structure
3. **Create assets** for all visual elements
4. **Test module combinations** for compatibility
5. **Polish and balance** the complete experience

This architecture ensures each module serves its purpose without conflicts, providing users with maximum flexibility and developers with clear responsibilities. 🌟
