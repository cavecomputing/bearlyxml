# BearlyXML

*It's "bearly" XML!*
```yaml
bearlyxml:
  version: v0.2
  goal: An easy to parse XML based character spec.
```

# ToDo
```xml
<todo status="in-progress">
Create tools to convert to character card spec. Separate python library. "tools" folder.
</todo>

<todo status="in-progress">
Map spec to character card format for SillyTavern.
</todo>
```
---
![pic](/bearlyxml.png)
Hola! 👋

This is the BearlyXML character spec I work on for when I create characters for stories, generally centered around LLM based roleplay. Yes, there are other formats already. Yes, most of them are useless (technically) and you should just write things in plaintext. BUT, I like to do things certain ways because I'm difficult like that and I like to make my methods open for other people to use if they want. The whole reason it is called "BearlyXML" is because I like bears and also it is like XML but my own custom format. So "bearly" XML.

# Spec
*Spec outlined below*
```xml
<bearlyxml>
  <spec>
    name: BearlyXML
    version: v0.2
  </spec>

  <instructions>
    [Narrative rules for the AI – e.g., show don't tell, no narration for {{user}}, autonomous characters, etc.]
  </instructions>

  <user name="{{user}}">
    name: string
    age: string
    ...
  </user>

  <setting>
    [Description of scene/setting]
  </setting>

  <character name="{{char}}" id="01">
    [Backstory text]
    <attributes>
      name: string
      age: string
      sexuality: string
      appearance: string, string, string
      ...
    </attributes>
  </character>

  <greetings>
    <greeting id="01">
      title: string
      greeting: string
    </greeting>
  </greetings>
</bearlyxml>
```
# Notes and Usage Guidelines

## Comment Syntax
Use `!` to write comments in BearlyXML. Comments are for internal notes and can be safely removed before processing. They should be ignored by parsers.

Example:
```xml
! This is a comment. It will be ignored.
```

## Usage Notes

- `<instructions>`:  
  - Required for **prompt-based roleplay**. Defines AI behavior, narrative style, and roleplay rules.  
  - **Ignored** during **character card conversion** for SillyTavern.

- `<user>`:  
  - Required for **prompt-based roleplay** to define the user role.  
  - **Ignored** in **character card conversion**.

- `<greetings>`:  
  - Not used in **prompt-based roleplay**.  
  - Used **only** in **character card conversion** (e.g., for SillyTavern).  
  - Included in output character cards.

## Key Sections by Use Case

| Section        | Prompt-Based Roleplay | SillyTavern Character Card |
|----------------|------------------------|----------------------------|
| `<instructions>` | ✅ Required            | ❌ Ignored                 |
| `<user>`         | ✅ Required            | ❌ Ignored                 |
| `<setting>`      | ✅ Optional            | ✅ Included                |
| `<character>`    | ✅ Required            | ✅ Included                |
| `<greetings>`    | ❌ Exclude             | ✅ Included                |

> **Note**: For prompt-based roleplay, include `<instructions>`, `<user>`, `<setting>`, and `<character>`.  
> For SillyTavern character card conversion, only `<setting>`, `<character>`, and `<greetings>` are used.
# Lore Books

This is a personal tracking system for lore book entries I plan to use in SillyTavern. It’s not part of BearlyXML. It’s just a way to organize and remember what lore I want to include later.

## Spec
Each entry is a YAML object with:
- `title`: A short name for the lore  
- `keywords`: A list of words or phrases that will trigger it  
- `description`: The text to be added when triggered  

Example:
```yaml
- Big Foot:
  keywords: Big Foot, cryptid, mountain
  description: |
    The elusive big foot himself standing over 8 feet tall with a fondness for diet pepsi.
```
