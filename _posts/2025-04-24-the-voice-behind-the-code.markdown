---
layout: post
title: The Voice Behind the Code
subtitle: 2025-04-24
description: Every creation has imprints of its creator.
category: draft
---

Every creation has imprints of its creator.

## Guess the Coder

When I was coding in a team, I liked to play a little game: I’d look at a piece of code and try to guess who wrote it. Then I’d check it with `git blame`. I don’t remember ever being wrong. I’d like to think it’s because I’m a code-whisperer genius — but it’s not. There had to be something in the code that my pattern recognition engine could latch on to. Something that allowed me to get an image of a distinct person on the other side of the code. The question is, what was that thing?

## Creative Choices

Every creative medium affords the creator a set of choices. In code we use tools to restrict that set of choices in the name of consistency. But even with linters, code reviews, style guides, etc. some choices always sneak through — and those are the ones that adds uniqueness to the coder's style. These are some of those choices:
- Naming
- File structure
- Formatting
- Use of language constructs
- Idioms
- Documentation

What follows are examples of each of these.
### Naming

Naming conventions can vary across countries and industries, even for the same concept.

```
// Coder A
type User struct {
    FirstName string
    LastName  string
}

// Coder B
type Person struct {
    Given  string
    Surname string
}
```

### File Structure

Architectural taste influences how you organize your files. In this example, one is more technical-modular; the other more domain-driven.

```
// Coder A (Functional focus)
project/
├── handlers/
├── models/
├── utils/
└── main.go

// Coder B (Domain focus)
project/
├── user/
│   ├── service.go
│   ├── repository.go
├── auth/
└── main.go
```

### Formatting

Coder A may value conciseness, while Coder B may be optimizing for readability and diff-friendliness.

```
# Coder A
if (is_valid and count > 0): result = compute(value)

# Coder B
if (
    is_valid
    and count > 0
):
    result = compute(value)
```

### Use of Language Constructs

Coder A prefers terseness; Coder B might be optimizing for clarity or debugging ease.

```
// Coder A
const status = error ? 'failed' : 'success';

// Coder B
let status;
if (error) {
    status = 'failed';
} else {
    status = 'success';
}
```

### Idioms

Idiomatic Go favors wrapping errors with context; the second version might reflect a background in verbose Java logging.

```
// Coder A (Go idiomatic)
if err != nil {
    return nil, fmt.Errorf("failed to load config: %w", err)
}

// Coder B (less idiomatic, Java-style)
if err != nil {
    log.Println("Error loading config:", err)
    return nil, err
}
```

### Documentation

Coder A uses structured docstrings, possibly for auto-generated docs. Coder B prefers informal inline commentary. Having no comments is a choice too.

```
# Coder A
def get_data():
    """Returns data from cache or fetches it."""
    ...

# Coder B
def get_data():
    # Try to load from cache. If cache is stale or missing, fetch.
    ...

```

## To Be Heard

In some of these dimensions there are only two options, but in most of them, like naming, there can be quite a lot of options depending on the context. Let's say that on average there are three options available, that'd mean that just based on these five dimensions we have 243 possible combinations of choices. More than enough for everyone on a small team to have a recognizable signature.

So what makes us recognize a particular coding voice? It’s partly the accumulated context — a pattern of choices we've seen before. And it’s partly what we know about the coder: their values, influences, and obsessions. When I see a domain focused structure, I think of Alice and her DDD rants. When it’s functionally organized, it smells like Bob, who sees everything through the lens of modular logic.

If we pay attention, if we really listen to the voice behind the code, we might catch a glimpse of what makes the creator tick and we might learn what they think about the craft that we love. 
