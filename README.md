# FontMetrics

## Overview
This library calculates text measurements using pre-generated font metrics data for specific fonts
and sizes.

For example, this library helps determine the width and height of text strings when rendered in
specific fonts and sizes.

This library was initially intended for use with the [Scenic](https://hex.pm/packages/scenic)
framework, but is also usable independently.

## Installation

Add `font_metrics` to your dependencies in `mix.exs` to install FontMetrics:

```elixir
def deps do
  [
    {:font_metrics, "~> 0.5"},
  ]
end
```

## Generating Metrics

Generate font metrics data using the [`truetype_metrics`](https://hex.pm/packages/truetype_metrics)
package from hex. You can also find metrics data for Roboto and RobotoMono in the Scenic project.

## 0.5 Update
Version 0.5 introduces major changes, including word boundary wrapping and corrects width
calculation issues.

It removes serialization in favor of returning the struct directly. This library should not dictate
how to serialize its data. We recommend using something like `:erlang.term_to_binary/2` for
serialization. Scenic no longer requires this functionality, which highlighted the need for this
change.
