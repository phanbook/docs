## Date

{{date}} Helper - Format a date using php

### Description

 Returns a string formatted according to the given format string using the given integer timestamp or the current time if no timestamp is given. In other words, timestamp is optional and defaults to the value of time(). 

```
string date ( string $format [, int $timestamp = time() ] )

```

For example:

```
{{ date("M j/y \a\t h:i", post.getCreatedAt() }}
{{ date('l jS \of F Y h:i:s A')}}

```

You can take look full documents at http://php.net/manual/en/function.date.php

