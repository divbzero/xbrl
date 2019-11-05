Features
---

- [ ] (P0) Parse XBRL instance documents
- [ ] (P0) Parse XBRL linkbases
  - [ ] (P2) Calculation linkbase
  - [ ] (P2) Definition linkbase
  - [ ] (P1) Label linkbase
  - [ ] (P0) Presentation linkbase
- [ ] (P0) Parse XBRL schemas

Classes
---

### XBRL Instance

#### Document

```python
class XBRL(list):
    """An XBRL instance document"""
    ...
```

#### Fact

```python
class Fact(dict):
    """An XBRL fact: concept, context, value"""
    ...
```

#### Concept

```python
class Concept(dict):
    """An XBRL concept"""
    ...
```

#### Context

```python
class Context(dict):
    """An XBRL context: company, segment, period"""
    ...
```

```python
class Period(dict):
    """An XBRL period: start date, end date"""
    ...
```

#### Value

```python
class Value(dict):
    """An XBRL value: amount, unit"""
    ...
```

```python
class Unit(dict):
    """An XBRL unit"""
    ...
```

### XBRL Linkbase

#### Linkbase

```python
class Linkbase(list):
    """An XBRL linkbase"""
    ...
```

```python
class CalculationLinkbase(Linkbase):
    """An XBRL calculation linkbase"""
    ...
```

```python
class DefinitionLinkbase(Linkbase):
    """An XBRL definition linkbase"""
    ...
```

```python
class LabelLinkbase(Linkbase):
    """An XBRL label linkbase"""
    ...
```

```python
class PresentationLinkbase(Linkbase):
    """An XBRL Presentation linkbase"""
    ...
```

#### Link

```python
class Link(dict):
    """An XBRL link"""
    ...
```

```python
class CalculationLink(Link):
    """An XBRL calculation link"""
    ...
```

```python
class DefinitionLink(Link):
    """An XBRL definition link"""
    ...
```

```python
class LabelLink(Link):
    """An XBRL label link"""
    ...
```

```python
class PresentationLink(Link):
    """An XBRL Presentation link"""
    ...
```

Usage
---

### XBRL Instance

```python
brka = XBRL(file='brka-20151231.xml')
brka = XBRL('BRKA', 2015)
brka = XBRL('BRKA', 2015, 'FY')
```

```python
brka = XBRL(file='brka-20160331.xml')
brka = XBRL('BRKA', 2016, 'Q1')
```

```python
facts = list(brka)
contexts = list(brka.contexts)
units = list(brka.units)
```

### XBRL Linkbase

```python
brka_cal = CalculationLinkbase(file='brka-20151231_cal.xml')
brka_cal = CalculationLinkbase('BRKA', 2015)
brka_cal = CalculationLinkbase('BRKA', 2015, 'FY')
```

```python
brka_def = DefinitionLinkbase(file='brka-20151231_def.xml')
brka_def = DefinitionLinkbase('BRKA', 2015)
brka_def = DefinitionLinkbase('BRKA', 2015, 'FY')
```

```python
brka_lab = LabelLinkbase(file='brka-20151231_lab.xml')
brka_lab = LabelLinkbase('BRKA', 2015)
brka_lab = LabelLinkbase('BRKA', 2015, 'FY')
```

```python
brka_pre = PresentationLinkbase(file='brka-20151231_pre.xml')
brka_pre = PresentationLinkbase('BRKA', 2015)
brka_pre = PresentationLinkbase('BRKA', 2015, 'FY')
```


