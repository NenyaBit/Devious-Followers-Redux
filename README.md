
# DISCLAIMER
# THIS IS NOT IN A PLAYABLE STATE. THERE ARE A LOT OF SCRIPTS FAILING TO COMPILE

# Compiling requirements

## Mod Sources

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

A repo containing headlined sources to all of these mods can be found here:
[Sources](https://github.com/MissCorruption/DFR-SOURCES)

## Tools

* Your favorite papyrus compiler
	* In my testing [Caprica](https://github.com/Orvid/Caprica), assumingly due to the amount of scripts
* [Spriggit](https://github.com/Mutagen-Modding/Spriggit)
	* Instructions on usage below

## Compiling/Building instructions

```
# Cloning the repo
git clone https://github.com/MissCorruption/Devious-Followers-Redux
cd DeviousFollowersRedux

# Building the ESP File
Path/To/Spriggit.CLI.exe deserialize --InputPath Source\ESP --OutputPath DeviousFollowers.esp
```


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
| DFR__TIF__0A27AEAD.psc | Missing function: `Prep` | `DFR_Events.psc` |
| DFR_Punish_Hunger.psc | Missing property: `ConfiscationContainer` | `_DFTools.psc` |
| DFR__TIF__0A38C725.psc | Missing function: `AcceptSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A38C727.psc | Missing functions: `RejectSlaveryRule()`, `NextSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A391875.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A39186F.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A391877.psc | Missing function: `RejectPun()` | `DFR_Events.psc` |
| DFR__TIF__0A39186D.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A39187C.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A38C760.psc | Missing function: `Prep` | `DFR_Events.psc` |
| DFR__TIF__0A38C726.psc | Missing function: `AcceptSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A38C767.psc | Missing function: `Prep` | `DFR_Events.psc` |
| DFR_EnslavementIntro_0A38C70F.psc | Missing functions: `NextSlaveryRule()`, `FinishSlaverySetup()` | QF__Gift_09000D62 |
| DFR__TIF__0A391876.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A38C729.psc | Missing function: `RejectSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A38C724.psc | Missing function: `AcceptSlaveryRule()` | `QF__DflowDealController_0A01C86D.psc` |
| DFR__TIF__0A391870.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A39186E.psc | Missing function: `SelectApology()` | `DFR_Events.psc` |
| DFR__TIF__0A39187D.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A400F6A.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager` |
| DFR__TIF__0A400F6B.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager` |
| DFR__TIF__0A400F6C.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager` |
| DFR__TIF__0A39187F.psc | Logic error: `type mismatch on parameter 1` | `_DFGoldConQScript` |
| DFR__TIF__0A400F6E.psc | Logic error: `cannot convert to unknown type dfr_outfitmanager` | `DFR_OutfitManager` |
| DFR__TIF__0A391887.psc | Missing function: `GiveGold()` | `_DFGoldConQScript.psc` |
| DFR__TIF__0A391892.psc | Missing function: `Delay` | `DFR_Events.psc` |
| DFR__TIF__0A39188C.psc | Missing function: `Prep` | `DFR_Events.psc` |
| DFR__TIF__0A39189B.psc | Missing function: `RejectPun()` | `DFR_Events.psc` |
| DFR__TIF__0A3E7A3F.psc | Missing function: `AcceptJob()` | `DFR_Events.psc` |
| DFR__TIF__0A3E7A41.psc | Missing function: `AcceptJob()` | `DFR_Events.psc` |
| DFR__TIF__0A39189C.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A39189D.psc | Missing function: `AcceptPun()` | `DFR_Events.psc` |
| DFR__TIF__0A3AFECA.psc | Missing function: `Prep` | `DFR_Events.psc` |
| DFR__TIF__0A41F61F.psc | Missing function: `StopRule()` | `DFR_Rules.psc` |
| DFR__TIF__0A3E7A40.psc | Missing function: `AcceptJob()` | `DFR_Events.psc` |
| DFR__TIF__0A429836.psc | Missing function: `StopRule()` | `DFR_Rules.psc` |
| TIF_Dflow_0810FCDD.psc | Missing function: `GiveWhoreArmor()` | `_DFTools.psc` |
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
| _Dx_TIF__09275DA2.psc | Missing function: `Prep` | `DFR_Events.psc` |
| tif__02017204.psc | Logic error: `cannot convert to unknown type tweakdfscript` | `tif__02017204.psc` |
| _Dx_TIF__09275DA1.psc | Missing function: `Prep` | `DFR_Events.psc` |
| _Dx_TIF__0A27AEA5.psc | Missing function: `Prep` | `DFR_Events.psc` |
| _Dx_TIF__0A27AEA9.psc | Missing function: `Prep` | `DFR_Events.psc` |
| _Dx_TIF__0A27AEA6.psc | Missing function: `Prep` | `DFR_Events.psc` |
| _Dx_TIF__0A27AEA8.psc | Missing function: `Prep` | `DFR_Events.psc` |
| _Dx_TIF__0A27AEA7.psc | Missing function: `Prep` | `DFR_Events.psc` |
| _Dx_TIF__0A27AEAA.psc | Missing function: `Prep` | `DFR_Events.psc` |

## Missing sources

I lack the sources of the files that have these functions and so does seemingly everyone else. While we have the dependecy sources, a lot of the functions missing should be present in DFR itself, which they are not.

# Future plans

Due to the lack of sources and lots of missing functions I'll be attempting to anti-redux some of these features, which may have been half implemented. It's the best course of action than trying to fill the blanks with dummy versions. Help from the commnity would be greatly appreciated!
