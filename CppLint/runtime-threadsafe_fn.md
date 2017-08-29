Pattern: Use of thread-unsafe function

Issue: -

## Description

Much code has been originally written without consideration of multi-threading. Also, engineers are relying on their old experience;
they have learned posix before threading extensions were added. This rule guide the engineers to use thread-safe functions (when using
posix directly).