---
title: "Consistency"
slug: consistency
date: 2020-12-18
categories: ["articles"]
keywords:
  - Programming
---

There are two bike stalls near my apartment. One is right in front of the door, the other around the corner. The one in front of the door is closest, so when I can, I store my bike there. However, most of the time that stall is full, and I need to go around the corner instead.

That's fine. Until a next morning–when I'm still in a daze because I'm not a morning person–I take the walk around the corner, only to realise my bike was actually in front of the door. The day before was one of those lucky days I could store my bike in front of the door.

I quit using the front stall. The less choices I have to make, the more room I have for important things.

<!--more-->

This mindset also affects the way I code. In a large projects we're working on, we often need form request objects. Form request objects take care of validating a requests, before they enter a controller.

```php
<?php

class UserRequest
{
    public function rules()
    {
        return ['name' => 'required'];
    }
}

class UserController
{
    public function edit(
        UserRequest $request,
        User $user
    ) {
        // …
    }
}
```

In this case, extracting that simple rule to a form request doesn't really benefit us, so we can just inline the rules in a  `$request->validate()` call.

```php
<?php

class UserController
{
    public function edit(Request $request, User $user)
    {
        $request->validate(['name' => 'required']);

        // …
    }
}
```

However, I needed to make a conscious decision: "Should I extract these rules to a form request?" In this case it was obvious. In other cases, It'll be obvious to use a form request object because I need to reuse the rules across multiple controllers. In the worst cases, it's a 50/50 split, depending on my mood the rules will or won't end up in a request object.

That's why we've decided to always use form objects, no matter how small. It removes a decision point when writing, and more importantly when reading code. If we need to debug the validation rule, we know exactly where to expect it. No 50/50 chance to end up in the wrong place.

The less choices we have to make, the more room we have to focus on the important parts of our code.
