Both function-based views (FBVs) and class-based views (CBVs) are in Django

When to Use FBVs or CBVs
> Some views are best implemented as CBVs, and others are best implemented as FBVs.

pic 1


Advantages of FBVs
- Less view code is better.
- Never repeat code in views.
- Views should handle presentation logic. Try to keep business logic in models when possible, or in forms if you must.
- Keep your views simple.
- Use them to write custom 403, 404, and 500 error handlers.
- Complex nested-if blocks are to be avoided.
