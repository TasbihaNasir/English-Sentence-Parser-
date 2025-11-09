# 📝 English Sentence Parser with PDA & CFG

A comprehensive English sentence validation system implementing Pushdown Automaton (PDA) and Context-Free Grammar (CFG) for syntactic analysis, demonstrating advanced Theory of Automata concepts including grammar rules, parse trees, and subject-verb agreement validation.

---

## ⚛️ Built With

- **Python 3** — Core programming language
- **NLTK (Natural Language Toolkit)** — CFG parsing and tree visualization
- **Custom PDA Implementation** — Stack-based sentence validation
- **Context-Free Grammar** — Formal language syntax rules

---

## 👨‍💻 Developers

| Name | Role | Institution |
|------|------|-------------|
| Tasbiha Nasir | Developer | FAST University |
| Madiha Aslam | Developer | FAST University |
| Uzair Hussain | Developer | FAST University |

**Course**: Theory of Automata (TOA)  
**Project Type**: Formal Language Theory & Parsing

---

## 🧩 System Overview

This project implements a dual-validation English sentence parser that combines:
1. **Custom PDA Simulator** - Stack-based recursive descent parser with subject-verb agreement checking
2. **NLTK CFG Parser** - Context-Free Grammar parser with visual parse tree generation

The system validates English sentences against comprehensive grammar rules, ensuring syntactic correctness and proper subject-verb agreement.

---

## 🗄️ Core Features

### 🔤 Grammar Coverage

#### Sentence Structures (S)
- **Simple Sentences**: NP + VP (Noun Phrase + Verb Phrase)
- **Present Simple**: "John eats"
- **Present Continuous**: "he is running"
- **Present Perfect**: "she has written"
- **With Modifiers**: Adjectives, Adverbs, Articles

#### Noun Phrases (NP)
- Pronouns (Singular: he/she/it, Plural: they)
- Nouns (Singular/Plural with articles)
- Modified Nouns (Adjective + Noun)
- Complex NPs (Article + Adjective + Noun)

#### Verb Phrases (VP)
- Simple verbs (eats, run)
- Continuous tenses (is eating, are running)
- Perfect tenses (has eaten, have written)
- With objects (eats apples)
- With adverbs (runs quickly)
- Complex VPs (has beautifully sung)

---

### ✅ Subject-Verb Agreement Validation

The PDA enforces proper agreement between subjects and verbs:

**Singular Subjects** require:
- Singular verbs (eats, runs)
- Singular auxiliaries (is, has)

**Plural Subjects** require:
- Plural verbs (eat, run)
- Plural auxiliaries (are, have)

**Examples**:
- ✅ "he eats" (Singular + Singular)
- ❌ "he eat" (Singular + Plural - Invalid)
- ✅ "they eat" (Plural + Plural)
- ❌ "they eats" (Plural + Singular - Invalid)

---

## 🎯 Theory of Automata Concepts

### 1. **Pushdown Automaton (PDA)**
- Stack-based parsing mechanism
- Recursive descent parsing
- State transitions based on grammar rules
- Subject number tracking for agreement

### 2. **Context-Free Grammar (CFG)**
- Production rules (S → NP VP)
- Terminal and non-terminal symbols
- Derivation trees
- NLTK grammar specification

### 3. **Parse Trees**
- Visual representation of sentence structure
- Hierarchical breakdown of constituents
- Syntax validation through tree generation

### 4. **Formal Language Theory**
- Grammar-based language definition
- Syntax vs semantics separation
- Finite vocabulary with infinite sentences

---

## 📚 Vocabulary Coverage

### Pronouns
- **Singular**: he, she, it
- **Plural**: they

### Nouns (11 singular, 9 plural)
- **Singular**: John, Mary, dog, cat, water, bread, juice, milk, house, car, apple
- **Plural**: dogs, cats, waters, breads, juices, milks, houses, cars, apples

### Verbs (60+ verbs in 4 forms)
- **Base Forms**: eat, run, jump, see, write, read, drink, speak, sleep, create, build, love, hate, help...
- **Singular Forms**: eats, runs, jumps, sees, writes, reads, drinks, speaks, sleeps...
- **Progressive (-ing)**: eating, running, jumping, seeing, writing, reading...
- **Past Participle**: eaten, run, jumped, seen, written, read, drunk, spoken, slept...

### Adjectives (35 adjectives)
big, small, beautiful, ugly, fast, slow, happy, sad, young, old, new, good, bad, easy, hard, bright, dark, strong, weak, clean, dirty, expensive, cheap, tall, short, intelligent, funny, kind, rude, generous, selfish, rich, poor, tired

### Adverbs (23 adverbs)
quickly, slowly, silently, loudly, happily, sadly, easily, hardly, brightly, darkly, strongly, weakly, cleanly, dirtily, expensively, cheaply, intelligently, kindly, rudely, generously, selfishly, beautifully

### Function Words
- **Articles**: a, an, the
- **Auxiliaries**: is, are (present continuous), has, have (present perfect)

---

## 🔄 System Architecture

### PDA Simulator Class

```python
class PDASimulator:
    def __init__(self):
        self.grammar = {...}      # Production rules
        self.terminals = {...}    # Terminal symbols
    
    def parse(tokens):
        # Recursive descent parsing
        # Stack-based validation
        # Subject-verb agreement checking
```

### Key Methods

1. **`parse(tokens)`** - Entry point for validation
2. **`_parse(tokens, stack, trace, subject_number)`** - Recursive parsing with:
   - Token matching
   - Stack manipulation
   - Production rule expansion
   - Subject number tracking and verification

---

## 🚀 Usage

### Installation

```bash
# Install NLTK
pip install nltk

# Run the program
python toa_final.py
```

### Running Pre-defined Tests

The program automatically validates 40+ pre-defined sentences:

```
Checking pre-defined sentences:

 Sentence: 'John eats'
🔹 Tokens: ['John', 'eats']

✅ PDA Accepted
✅ Valid Sentence

 Sentence: 'they runs'
🔹 Tokens: ['they', 'runs']

❌ PDA Rejected
❌ Invalid Sentence
```

### Interactive Mode

```
Do you want to check more sentences? (y/n): y

Enter your sentence: she is running
✅ PDA Accepted
✅ Valid Sentence

Do you want to enter another sentence? (y/n): n
```

---

## 📊 Example Validations

### ✅ Valid Sentences

```
"John eats"                          → Simple present
"they eat"                           → Plural agreement
"he is running"                      → Present continuous
"they are running"                   → Plural continuous
"she has written"                    → Present perfect
"they have eaten apples"             → Perfect with object
"the tired cat has slept"            → With adjectives
"he has written quickly"             → With adverb
"John is quickly running"            → Adverb placement
"she has beautifully sung"           → Complex adverb
```

### ❌ Invalid Sentences

```
"they runs"                          → Wrong verb form
"Mary are running"                   → Wrong auxiliary
"he drinking"                        → Missing auxiliary
"she have eaten"                     → Wrong auxiliary
"he have written"                    → Agreement error
"they has eaten"                     → Agreement error
"John has jump"                      → Wrong participle
"John has eating"                    → Wrong verb form
"he is eaten"                        → Wrong tense structure
```

---

## 🎨 Parse Tree Visualization

For valid sentences, the system generates visual parse trees:

```
                    S                
        ____________|____________     
       NP                       VP   
       |                    ____|___  
  SingularPronoun          |       NP
       |                   |        | 
       he              SingularVerb  |
                           |         |
                         eats    Article
                                     |
                                    the
```

---

## 📁 File Structure

```
English-Parser/
│
├── toa_final.py                # Main program
│
├── Components/
│   ├── PDA Simulator           # Custom pushdown automaton
│   ├── NLTK CFG Parser         # Context-free grammar parser
│   └── Validation System       # Dual-validation logic
│
└── README.md
```

---

## 🔍 Grammar Production Rules

### Core Rules
```
S → NP VP
NP → SingularPronoun | PluralPronoun | SingularNoun | PluralNoun
NP → Article SingularNoun | Article PluralNoun
NP → Adjective SingularNoun | Adjective PluralNoun
VP → SingularVerb | PluralVerb
VP → SingularAux VerbING | PluralAux VerbING
VP → pastparticipleAUXS PastParticiple | pastparticipleAUXP PastParticiple
```

### Extended Rules
```
VP → SingularVerb NP | PluralVerb NP
VP → SingularAux VerbING NP | PluralAux VerbING NP
VP → pastparticipleAUXS PastParticiple NP | pastparticipleAUXP PastParticiple NP
VP → SingularVerb Adverb | PluralVerb Adverb
VP → pastparticipleAUXS PastParticiple Adverb | pastparticipleAUXP PastParticiple Adverb
```

---

## ⚙️ Technical Implementation

### PDA Stack Operations

```python
# Stack-based parsing
stack = ["S"]
tokens = ["John", "eats"]

# Expand S → NP VP
stack = ["VP", "NP"]

# Match NP with "John"
stack = ["VP"]

# Match VP with "eats"
stack = []  # ✅ Accepted
```

### Subject-Verb Agreement Logic

```python
# Track subject number
if NP → SingularNoun:
    subject_number = "singular"

# Verify VP matches
if VP → SingularVerb and subject_number == "singular":
    ✅ Valid
else:
    ❌ Reject production
```

---

## 🎓 Educational Value

This project demonstrates:
- ✅ PDA implementation from scratch
- ✅ CFG rule definition
- ✅ Parse tree generation
- ✅ Syntax validation
- ✅ Subject-verb agreement checking
- ✅ Recursive descent parsing
- ✅ Formal language theory application

---

## 🚨 Input Guidelines

### Rules for User Input

1. **Capitalization**: Only capitalize proper nouns (John, Mary)
2. **Grammar**: Follow subject + verb + object structure
3. **Punctuation**: Not required
4. **Vocabulary**: Use only provided words
5. **Complexity**: Simple sentences only (no compound/complex)
6. **Tenses**: Present simple, continuous, and perfect only

### Example Valid Inputs
```
"he is eating"
"they have written"
"the big dog runs"
"she has beautifully sung"
```

---

## 🔮 Future Enhancements

- [ ] Support for compound sentences
- [ ] Past tense implementation
- [ ] Future tense structures
- [ ] Question sentence parsing
- [ ] Negative sentence structures
- [ ] Modal verb support (can, will, should)
- [ ] Prepositional phrases
- [ ] Subordinate clauses
- [ ] Semantic analysis layer
- [ ] Error correction suggestions
- [ ] Probability-based parsing (PCFG)
- [ ] Machine learning integration

---

## 📊 Test Coverage

### Pre-defined Test Cases: 40+ sentences
- ✅ Subject-verb agreement (positive/negative)
- ✅ Tense validation
- ✅ Article usage
- ✅ Adjective placement
- ✅ Adverb positioning
- ✅ Auxiliary verb correctness
- ✅ Complex sentence structures

---

## 🐛 Limitations

- No compound/complex sentence support
- Limited to three tenses (present simple, continuous, perfect)
- Fixed vocabulary set
- No semantic validation
- No error correction suggestions
- Single sentence processing only

---


## 📄 License

Educational project created for FAST University Theory of Automata course.

---

## 🏁 Conclusion

This English Sentence Parser demonstrates practical application of formal language theory, combining PDA and CFG to create a robust syntax validator with subject-verb agreement checking. The project showcases the power of automata theory in natural language processing.

---

**💡 Developed By**

Tasbiha Nasir, Madiha Aslam, and Uzair Hussain  
*Theory of Automata Project*  
*FAST University*
