# BearlyXML

*It's "bearly" XML!*
```yaml
bearlyxml:
  version: v0.1
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

This is the BearlyXML character spec format I created for when I create characters for stories, generally centered around AI based roleplay. Yes, there are other formats already. Yes, most of them are useless (technically) and you should just write things in plaintext. BUT, I like to do things certain ways because I'm difficult like that and I like to make those methods open for other people to use if they want. 

**Note**: This is a heavy work in progress and a few things are missing from this repo I intend to add for making this spec easier to use.
# Spec
*Spec outlined below*
```xml
<spec>
name: BearlyXML
version: v0.1
</spec>

<setting>
Explanation of setting.
</setting>

<character name="{{char}}">
Text backstory.
<metainfo>
name: [name]
age: [age]
sexuality: [sexuality]
appearance: [descrip 1, descript 2, descrip 3]
...
</metainfo>
</character>

<user name="{{user}}">
reserved for use in prompt only rp
name: [name]
age: [age]
...
</user>

---

<greetings>
<greeting_1>
title: ...
greeting: ...
</greeting_1>

<greeting_2>
title: ...
greeting: ...
</greeting_2>
</greetings>
```
