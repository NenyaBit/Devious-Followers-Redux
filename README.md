
# The Road ahead

As you can see the DFR 0.4.5 is quite the mess. `.pex` files don't match the `.psc` ones when decompiled, functions are called that no longer exist or where meant to exist at some point and so on. It's such a mess you can hardly begin to recreate what the functions were supposed to do.

As such, I'll be attempting to rewrite DFR bit by bit, or rule by rule, starting with Gold. To avoid confusion on which files have been reworked and which didn't, all my work will use `DFRX` as prefix. If you plan to help by contributing, please also use said prefix. 

I welcome any contributions! From bugfixes, to a wiki explaining how a rule is supposed to work and so on. Before I can work on feature requests I want to get DFR in a workable state. Meaning you compile the sources, no scripts fail to compile and it functions in game. If a rule breaks or similar, that's fine.

If you are struggling with Spriggit or don't know how to de/serialize the ESP, just ask me. I can manage that part.

### What about Adversity Framework and Helping Hand?

I talked with Scrab a lot in Nua's Server. She has plans to move some systems from DFR into AF and such, so before people rework those bits you'll have to wait for Scrab to implement the functions. 

In short: Leave anything relating to AF and HH alone *for now*.

By extension, there are currently no plans to maintain `Dealer's Choice`, at least not by me nor Scrab. It's contents may be considered after core DFR is stable.


### I want to help!

As described above you don't need coding knowledge to help. Describing how a rule worked, or was supposed to work is already helping. If you want to help by contributing code, consider the following:

* This repository does *not* contain an ESP file.
	- I'm utilizing [Spriggit](https://github.com/Mutagen-Modding/Spriggit) to serialize it. In short, turn the ESP into a bunch of .yml files to actually keep track of changes. More information can be found below.
* You will need basic knowledge of [Git](https://git-scm.com/) and how Forks work.
	- I prefer having people fork the project, do their changes and then create a [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) back to this respository. I don't want to see several DFR versions available, all adding/fixing a little thing and being incompatible with one another. 
* Please use the `DFRX` prefix when creating/editing things in CK.
	- This helps me and others to keep track of what has been reworked and what hasn't.

I plan to implement/maintain DFR this way:

1. Anything new, reworked or overhauled uses the `DFRX` prefix.
2. Each rule is isolted into it's own Quest in CK.
3. Some systems will be removed due to either being too incomplete or them being reimplemented in AF directly.
4. This repository should stay the definitive and main respository of DFR. I have nothing against Forks, I just want to give users a one-stop solution.
5. Before any new feature gets added the core mod should function in a desired way.
	- A new feature I was joking around with was an uno reverse card. You being the Devious one instead of your follower, but that comes at a later date.

### Requirements

#### Tools

* Your favorite papyrus compiler
	* In my testing [Caprica](https://github.com/Orvid/Caprica) did not work, assumingly due to the amount of scripts
* [Git](https://git-scm.com/downloads)
* [Spriggit](https://github.com/Mutagen-Modding/Spriggit)
	* Instructions on usage for the CLI version are below

#### Mod Sources/Script files

You'll need *all* of those mods installed, or imported in your `.ppj` file to compile DFR (at least those scripts that can compile).

- Adversity Framework
- Devious Devices
- Dealers Choice
- Extensible Follower Framework
- Helping Hand
- Milk Mod Economy
- PapyrusUtil
- Practical Defeat (Reanimated)
- PowerOfThree's Papyrus Extender
- SkyUI
- SexLab Aroused
- Spank that Ass
- SexLab
- UI Extensions

For your (and my) convenience I created another respository that hosts headlined scripts from all of those mods. Headlined means functions were truncated to not contain code, only the names and signatures. This allows us to compile without running into a "dependency spiral" due to soft deps. These scripts should *not* be used for gameplay!

They were headlined using the [PapyrusSourceHeadliner](https://github.com/IHateMyKite/PAPYRUS).

### [Headlined Sources](https://github.com/MissCorruption/DFR-SOURCES)


#### De/Serializing the .yaml files to/from an ESP 

`Serializing` refers to turning the ESP file, which is binary, into several .yaml files. Why? When making changes to an ESP and uploading said ESP to Github you won't be able to see any diff because it's a binary upload. With serializing you can keep track of changes and even fix small things by editing the `.yaml` files!


```bat
# Cloning the repo
git clone https://github.com/MissCorruption/Devious-Followers-Redux
cd Devious-Followers-Redux

# Serializing the ESP File
Path/To/Spriggit.CLI.exe serialize --InputPath DeviousFollowers.esp --OutputPath Source\ESP


# Deserializing the ESP File
Path/To/Spriggit.CLI.exe deserialize --InputPath Source\ESP --OutputPath DeviousFollowers.esp
```

---

# INFORMATION BELOW THIS POINT IS KEPT FOR DOCUMENTARY PURPOSES

---

# Known issues

## Compiling

Below is a table of scripts that will not compile, the reason why and which script is at fault:

| Failing to compile | Reason | Script at fault |
|--------------------|--------|-----------------|
| DFR__TIF__0A02E5A2.psc | Missing function: `Done` | `HH_Makeup.psc` from *Helping Hand* |
| DFR__TIF__0A02E5A3.psc | Missing function: `Done` | `HH_Makeup.psc` from *Helping Hand* |
| DFR__TIF__0A02E354.psc | Missing function: `CheckHorse` | `HH_Hostler.psc` from *Helping Hand* |
| DFR__TIF__0A02E5A4.psc | Missing function: `Done` | `HH_Makeup.psc` from *Helping Hand* |
| DFR_Slavery.psc | Missing function: `SetStageSlavery` | `DFR_RelationshipManager.psc` |
| DFR_Punish_Hunger.psc | Missing property: `ConfiscationContainer` | `_DFTools.psc` |
| DFR__TIF__0A38C725.psc | Missing function: `AcceptSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A38C727.psc | Missing functions: `RejectSlaveryRule()`, `NextSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A391875.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A39186F.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A391877.psc | Missing function: `RejectPun()` | `DFR_Events.psc` |
| DFR__TIF__0A39186D.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A39187C.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A38C726.psc | Missing function: `AcceptSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR_EnslavementIntro_0A38C70F.psc | Missing functions: `NextSlaveryRule()`, `FinishSlaverySetup()` | `QF__Gift_09000D62.psc` |
| DFR__TIF__0A391876.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A38C729.psc | Missing function: `RejectSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A38C724.psc | Missing function: `AcceptSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A391870.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A39186E.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A39187D.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A400F6A.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager.psc` |
| DFR__TIF__0A400F6B.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager.psc` |
| DFR__TIF__0A400F6C.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager.psc` |
| DFR__TIF__0A39187F.psc | Logic error: `type mismatch on parameter 1` | `_DFGoldConQScript.psc` |
| DFR__TIF__0A400F6E.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager.psc` |
| DFR__TIF__0A391887.psc | Missing function: `GiveGold()` | `_DFGoldConQScript.psc` |
| DFR__TIF__0A391892.psc | Missing function: `Delay` | `DFR_Events.psc` |
| DFR__TIF__0A39189B.psc | Missing function: `RejectPun()` | `DFR_Events.psc` |
| DFR__TIF__0A3E7A3F.psc | Missing function: `AcceptJob()` | `DFR_Events.psc` |
| DFR__TIF__0A3E7A41.psc | Missing function: `AcceptJob()` | `DFR_Events.psc` |
| DFR__TIF__0A39189C.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A39189D.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A41F61F.psc | Missing function: `StopRule()` | `DFR_Rules.psc` |
| DFR__TIF__0A3E7A40.psc | Missing function: `AcceptJob()` | `DFR_Events.psc` |
| DFR__TIF__0A429836.psc | Missing function: `StopRule()` | `DFR_Rules.psc` |
| DFR__TIF__0A429833.psc | Missing function: `StopRule()` | `DFR_Rules.psc` |
| DFR__TIF__0A3E7A43.psc | Missing function: `AcceptJob()` | `DFR_Events.psc` |
| DFR__TIF__0A42983C.psc | Missing function: `StopRule()` | `DFR_Rules.psc` |
| TIF_Dflow_081173BB.psc | Logic error: `argument a is not specified and has no default value` | `TIF_Dflow_081173BB.psc` |
| DFR__TIF__0A429839.psc | Missing function: `StopRule()` | `DFR_Rules.psc` |
| TIF_Dflow_08070DAA.psc | Missing function: `PGropeFail()` | `_DFTools.psc` |
| tif__02006eac.psc | Logic error: `tweakdfscript is not a known user-defined type` | `tif__02006eac.psc` |
| TIF_Dflow_090C28E7.psc | Missing property: `Alias_JarlPetGame` | `qf__dflowgames_0a0110dc.psc` |
| tif__0204b694.psc | Logic error: `cannot convert to unknown type tweakdfscript` | `tif__0204b694.psc` |
| tif__02006ebb.psc | Logic error: `cannot convert to unknown type tweakdfscript` | `tif__02006ebb.psc` |
| tif__02006ebf.psc | Logic error: `cannot convert to unknown type tweakdfscript` | `tif__02006ebf.psc` |
| tif__02017204.psc | Logic error: `cannot convert to unknown type tweakdfscript` | `tif__02017204.psc` |