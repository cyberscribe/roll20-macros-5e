# Roll20 Macros for 5e
*Useful macros for playing 5eOGL on the roll20 virtual tabletop platform*

### Init
*Rolls initiative for selected token and adds to turn tracker*

    `%{selected|npc_init}`

### Check
*Displays a drop-down menu with all abilities and their associated skills for the selected token, rolls whatever is picked*

![Screenshot of check macro drop-down menu](https://raw.githubusercontent.com/cyberscribe/roll20-macros-5e/master/check.png)


    &{template:simple}  {{mod=?{Skill|STRENGTH (@{selected|strength_mod}), [[@{selected|strength_mod}]] Strength |&nbsp;&nbsp;&nbsp;&nbsp;Athletics (@{selected|athletics_bonus}), [[@{selected|athletics_bonus}]] Athletics|DEXTERITY (@{selected|dexterity_mod}), [[@{selected|dexterity_mod}]] Dexterity |&nbsp;&nbsp;&nbsp;&nbsp;Acrobatics (@{selected|acrobatics_bonus}), [[@{selected|acrobatics_bonus}]] Acrobatics|&nbsp;&nbsp;&nbsp;&nbsp;Sleight of Hand (@{selected|sleight_of_hand_bonus}), [[@{selected|sleight_of_hand_bonus}]] Sleight of Hand|&nbsp;&nbsp;&nbsp;&nbsp;Stealth (@{selected|stealth_bonus}), [[@{selected|stealth_bonus}]] Stealth|CONSTITUTION (@{selected|constitution_mod}), [[@{selected|constitution_mod}]] Constitution|INTELLIGENCE (@{selected|intelligence_mod}), [[@{selected|intelligence_mod}]] Intelligence|&nbsp;&nbsp;&nbsp;&nbsp;Arcana (@{selected|arcana_bonus}), [[@{selected|arcana_bonus}]] Arcana|&nbsp;&nbsp;&nbsp;&nbsp;History (@{selected|history_bonus}), [[@{selected|history_bonus}]] History|&nbsp;&nbsp;&nbsp;&nbsp;Investigation (@{selected|investigation_bonus}), [[@{selected|investigation_bonus}]] Investigation|&nbsp;&nbsp;&nbsp;&nbsp;Nature (@{selected|nature_bonus}), [[@{selected|nature_bonus}]] Nature|&nbsp;&nbsp;&nbsp;&nbsp;Religion (@{selected|religion_bonus}), [[@{selected|religion_bonus}]] Religion|WISDOM (@{selected|wisdom_mod}), [[@{selected|wisdom_mod}]] Wisdom|&nbsp;&nbsp;&nbsp;&nbsp;Animal Handling (@{selected|animal_handling_bonus}), [[@{selected|animal_handling_bonus}]] Animal Handling|&nbsp;&nbsp;&nbsp;&nbsp;Insight (@{selected|insight_bonus}), [[@{selected|insight_bonus}]] Insight|&nbsp;&nbsp;&nbsp;&nbsp;Medicine (@{selected|medicine_bonus}), [[@{selected|medicine_bonus}]] Medicine|&nbsp;&nbsp;&nbsp;&nbsp;Perception (@{selected|perception_bonus}), [[@{selected|perception_bonus}]] Perception|&nbsp;&nbsp;&nbsp;&nbsp;Survival (@{selected|survival_bonus}), [[@{selected|survival_bonus}]] Survival|CHARISMA (@{selected|charisma_mod}), [[@{selected|charisma_mod}]] Charisma|&nbsp;&nbsp;&nbsp;&nbsp;Deception (@{selected|deception_bonus}), [[@{selected|deception_bonus}]] Deception|&nbsp;&nbsp;&nbsp;&nbsp;Intimidation (@{selected|intimidation_bonus}), [[@{selected|intimidation_bonus}]] Intimidation|&nbsp;&nbsp;&nbsp;&nbsp;Persuasion (@{selected|persuasion_bonus}), [[@{selected|persuasion_bonus}]] Persuasion|&nbsp;&nbsp;&nbsp;&nbsp;Performance (@{selected|performance_bonus}), [[@{selected|performance_bonus}]] Performance
    } }} {{rname=CHECK
    }} {{r1=[[1d20+?{Skill}]]}} {{always=1}} {{r2=[[1d20+?{Skill}]]}} {{charname=@{selected|token_name} }}

### Save
*Displays a drop-down menu with all saving throw types (i.e. abilities) for the selected token, rolls whatever is picked*

![Screenshot of save macro drop-down menu](https://raw.githubusercontent.com/cyberscribe/roll20-macros-5e/master/save.png)

    &{template:simple}  {{mod=?{Skill|Strength (@{selected|strength_save_bonus}), [[@{selected|strength_save_bonus}]] Strength |Dexterity (@{selected|dexterity_save_bonus}), [[@{selected|dexterity_save_bonus}]] Dexterity |Constitution (@{selected|constitution_save_bonus}), [[@{selected|constitution_save_bonus}]] Constitution|Intelligence (@{selected|intelligence_save_bonus}), [[@{selected|intelligence_save_bonus}]] Intelligence|Wisdom (@{selected|wisdom_save_bonus}), [[@{selected|wisdom_save_bonus}]] Wisdom|Charisma (@{selected|charisma_save_bonus}), [[@{selected|charisma_save_bonus}]] Charisma
    } }} {{rname=SAVE
    }} {{r1=[[1d20+?{Skill}]]}} {{always=1}} {{r2=[[1d20+?{Skill}]]}} {{charname=@{selected|token_name} }}

### Spells
*Credit to [AndruC](https://gist.github.com/AndruC/454c3242917050a0dadd44956dade699)*

    &{template:default}{{name=@{selected|character_name} Spellcasting
    }}{{ Spell DC @{selected|spell_save_dc} = @{selected|spell_attack_bonus} to hit with spell attacks
    }}{{ Cantrips = [@{selected|repeating_spell-cantrip_$0_spellname}](~selected|repeating_spell-cantrip_$0_spell)
    }}{{ 1st (SLOTS) = [@{selected|repeating_spell-1_$0_spellname}](~selected|repeating_spell-1_$0_spell)
    }}{{ 2nd (SLOTS) = [@{selected|repeating_spell-2_$0_spellname}](~selected|repeating_spell-2_$0_spell)
    }}{{ 3rd (SLOTS) = [@{selected|repeating_spell-3_$0_spellname}](~selected|repeating_spell-3_$0_spell)
    }}
