# 1cApacheWebService
Настройки  web-сервера apache
[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggVERcbiAgICBhcGFjaGVbZmE6ZmEtZm9sZGVyIC9ob21lL29lbS9lc2luYS9hcGFjaGVdIFxuICAgIGFwYWNoZSAtLS0gfCDQlNC-0YHRgtGD0L_QvdGL0LUg0LzQvtC00YPQu9C4IHwgbW9kc1tmYTpmYS1mb2xkZXIgbW9kcy1hdmFpbGFibGVdXG4gICAgYXBhY2hlIC0tLS0gfCDQlNC-0YHRgtGD0L_QvdGL0LUg0YHQsNC50YLRiyB8IHNpdGVzW2ZhOmZhLWZvbGRlciBzaXRlcy1hdmFpbGFibGVdXG4gICAgYXBhY2hlIC0tLSB8INCd0LDRgdGC0YDQvtC50LrQuCDQutC70LjQtdC90YLQvtCyIDHQoS3QsdCw0LcgfHZyZFtmYTpmYS1mb2xkZXIgdnJkLWZpbGVzXVxuXG4gICAgbW9kcyAtLS0gfCDQndCw0YHRgtGA0L7QudC60LAg0LzQvtC00YPQu9GPIGFwYWNoZSB8IHdzYXAyNC5jb25mW2ZhOmZhLWZpbGUgd3NhcDI0LmNvbmZdXG4gICAgbW9kcyAtLS0gfCDQl9Cw0LPRgNGD0LfQutCwINC80L7QtNGD0LvRjyBhcGFjaGUgfCB3c2FwMjQubG9hZFtmYTpmYS1maWxlIHdzYXAyNC5sb2FkXVxuXG4gICAgc2l0ZXMgLS0tIHwg0JzQvtC00YPQu9C4INC60L7QvdGE0LjQs9GD0YDQsNGG0LjQuCDQvtGB0L3QvtCy0L3QvtCz0L4g0YHQsNC50YLQsCB8IGRlZltmYTpmYS1mb2xkZXIgMDAwLWRlZmF1bHRdXG4gICAgc2l0ZXMgLS0tIHwg0JrQvtC90YTQuNCz0YPRgNCw0YbQuNGPINC-0YHQvdC-0LLQvdC-0LPQviDRgdCw0LnRgtCwIHwgZGVmLmNvbmZbZmE6ZmEtZmlsZSAwMDAtZGVmYXVsdC5jb25mXVxuXG4gICAgZGVmIC0tLSB8INCU0L7RgdGC0YPQv9C90YvQtSDQutC-0L3RhNC40LPRg9GA0LDRhtC40LggMdChLdCx0LDQtyB8IGF2YWlsYWJsZVtmYTpmYS1mb2xkZXIgYXZhaWxhYmxlXVxuICAgIGRlZiAtLS0gfCDQkNC60YLQuNCy0L3Ri9C1INC60L7QvdGE0LjQs9GD0YDQsNGG0LjQuCAx0KEt0LHQsNC3IHwgZW5hYmxlZFtmYTpmYS1mb2xkZXIgZW5hYmxlZF1cbiAgICBkZWYgLS0tIHwg0J7QsdGJ0LjQtSDQvdCw0YHRgtGA0L7QudC60Lgg0LrQvtC90YTQuNCz0YPRgNCw0YbQuNC5IDHQoS3QsdCw0LcgfCBkaXJlY3RvcnkuY29uZltmYTpmYS1maWxlIGRpcmVjdG9yeS5jb25mXVxuXG4gICAgYXZhaWxhYmxlID09PSB8INCk0LDQudC70Ysg0LrQvtC90YTQuNCz0YPRgNCw0YbQuNC5IDHQoS3QsdCw0LcgfCBmaWxlLmNvbmZbZmE6ZmEtZmlsZSAqLmNvbmZdXG4gICAgZW5hYmxlZCA9PT0gfCDQodGB0YvQu9C60Lgg0L3QsCDRhNCw0LnQu9GLINC60L7QvdGE0LjQs9GD0YDQsNGG0LjQuSAx0KEt0LHQsNC3IHwgbGluay5jb25mW2ZhOmZhLWxpbmsgKi5jb25mXVxuICAgIFxuICAgIGxpbmsuY29uZiAtLi0-IHwg0JLQutC7L9CS0YvQutC7INGBINC_0L7QvNC-0YnRjNGOINGB0YHRi9C70LrQuCB8IGZpbGUuY29uZlxuXG4gICAgdnJkID09PSB8INCa0LDRgtCw0LvQvtCz0Lgg0LrQu9C40L3RgtC-0LIg0LHQvtC10LLQvtC5IDHQoS3QsdCw0LfRiyB8IHByb2RbZmE6ZmEtZm9sZGVyICoucHJvZF1cbiAgICBwcm9kIC0tLSB8INCa0LDRgtCw0LvQvtCzINC60LvQuNC10L3RgtCwIDHQoS3QsdCw0LfRiyDRgNCw0LfRgNCw0LHQvtGC0LrQuCB8IGRldltmYTpmYS1mb2xkZXIgZGV2XVxuICAgIFxuICAgIHByb2QgLS0tIHwg0J3QsNGB0YLRgNC-0LnQutCwINC60LvQuNC10L3RgtCwINCx0L7QtdCy0L7QuSAx0KEt0LHQsNC30YsgfCBwcm9kLnZyZFtmYTpmYS1maWxlIHByb2QudnJkXVxuICAgIGRldiAtLS0gfCDQndCw0YHRgtGA0L7QudC60LAg0LrQu9C40LXQvdGC0LAgMdChLdCx0LDQt9GLINGA0LDQt9GA0LDQsdC-0YLQutC4IHwgZGV2LnZyZFtmYTpmYS1maWxlIGRldi52cmRdXG4gICAgXG4gICAgZGVmLmNvbmYgLS0-IGxpbmsuY29uZlxuICAgIGZpbGUuY29uZiAtLT4gZGlyZWN0b3J5LmNvbmZcbiAgICBmaWxlLmNvbmYgLS0-IHByb2QudnJkXG4gICAgZmlsZS5jb25mIC0tPiBkZXYudnJkXG5cbiAgICBhcGFjaGUyW2ZhOmZhLWZvbGRlciAvZXRjL2FwYWNoZTJdXG4gICAgYXBhY2hlMiAtLS0gc2l0ZXMtYXZhaWxhYmxlW2ZhOmZhLWZvbGRlciBzaXRlcy1hdmFpbGFibGVdXG4gICAgYXBhY2hlMiAtLS0gbW9kcy1hdmFpbGFibGVbZmE6ZmEtZm9sZGVyIG1vZHMtYXZhaWxhYmxlXVxuXG4gICAgbW9kcy1hdmFpbGFibGUgLS0tIGxpbmsud3NhcDI0LmNvbmZbZmE6ZmEtbGluayB3c2FwMjQuY29uZl1cbiAgICBtb2RzLWF2YWlsYWJsZSAtLS0gbGluay53c2FwMjQubG9hZFtmYTpmYS1saW5rIHdzYXAyNC5sb2FkXVxuXG4gICAgbGluay53c2FwMjQuY29uZiAtLi4tPiB3c2FwMjQuY29uZlxuICAgIGxpbmsud3NhcDI0LmxvYWQgLS4uLT4gd3NhcDI0LmxvYWRcblxuICAgIHNpdGVzLWF2YWlsYWJsZSAtLS0gZXRjLmRlZi5jb25mW2ZhOmZhLWxpbmsgMDAwLWRlZmF1bHQuY29uZl1cbiAgICBldGMuZGVmLmNvbmYgLS4tPiBkZWYuY29uZlxuXG4gICAgZGlzdHJpYltmYTpmYS1mb2xkZXIgL2hvbWUvb2VtL2VzaW5hL2Rpc3RyaWJdID09PSB2ZXJzaW9uW2ZhOmZhLWZvbGRlciB2ZXJzaW9uL29wdC8xQy92OC4zL3g4Nl82NF1cbiAgICBwbGF0Zm9ybVtmYTpmYS1saW5rIC9ob21lL29lbS9lc2luYS9wbGF0Zm9ybV0gLS4tPiB2ZXJzaW9uXG5cbiAgICB3c2FwMjQubG9hZCAtLT4gcGxhdGZvcm0iLCJtZXJtYWlkIjp7InRoZW1lIjoiZGVmYXVsdCJ9LCJ1cGRhdGVFZGl0b3IiOnRydWUsImF1dG9TeW5jIjp0cnVlLCJ1cGRhdGVEaWFncmFtIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/edit#eyJjb2RlIjoiZ3JhcGggVERcbiAgICBhcGFjaGVbZmE6ZmEtZm9sZGVyIC9ob21lL29lbS9lc2luYS9hcGFjaGVdIFxuICAgIGFwYWNoZSAtLS0gfCDQlNC-0YHRgtGD0L_QvdGL0LUg0LzQvtC00YPQu9C4IHwgbW9kc1tmYTpmYS1mb2xkZXIgbW9kcy1hdmFpbGFibGVdXG4gICAgYXBhY2hlIC0tLS0gfCDQlNC-0YHRgtGD0L_QvdGL0LUg0YHQsNC50YLRiyB8IHNpdGVzW2ZhOmZhLWZvbGRlciBzaXRlcy1hdmFpbGFibGVdXG4gICAgYXBhY2hlIC0tLSB8INCd0LDRgdGC0YDQvtC50LrQuCDQutC70LjQtdC90YLQvtCyIDHQoS3QsdCw0LcgfHZyZFtmYTpmYS1mb2xkZXIgdnJkLWZpbGVzXVxuXG4gICAgbW9kcyAtLS0gfCDQndCw0YHRgtGA0L7QudC60LAg0LzQvtC00YPQu9GPIGFwYWNoZSB8IHdzYXAyNC5jb25mW2ZhOmZhLWZpbGUgd3NhcDI0LmNvbmZdXG4gICAgbW9kcyAtLS0gfCDQl9Cw0LPRgNGD0LfQutCwINC80L7QtNGD0LvRjyBhcGFjaGUgfCB3c2FwMjQubG9hZFtmYTpmYS1maWxlIHdzYXAyNC5sb2FkXVxuXG4gICAgc2l0ZXMgLS0tIHwg0JzQvtC00YPQu9C4INC60L7QvdGE0LjQs9GD0YDQsNGG0LjQuCDQvtGB0L3QvtCy0L3QvtCz0L4g0YHQsNC50YLQsCB8IGRlZltmYTpmYS1mb2xkZXIgMDAwLWRlZmF1bHRdXG4gICAgc2l0ZXMgLS0tIHwg0JrQvtC90YTQuNCz0YPRgNCw0YbQuNGPINC-0YHQvdC-0LLQvdC-0LPQviDRgdCw0LnRgtCwIHwgZGVmLmNvbmZbZmE6ZmEtZmlsZSAwMDAtZGVmYXVsdC5jb25mXVxuXG4gICAgZGVmIC0tLSB8INCU0L7RgdGC0YPQv9C90YvQtSDQutC-0L3RhNC40LPRg9GA0LDRhtC40LggMdChLdCx0LDQtyB8IGF2YWlsYWJsZVtmYTpmYS1mb2xkZXIgYXZhaWxhYmxlXVxuICAgIGRlZiAtLS0gfCDQkNC60YLQuNCy0L3Ri9C1INC60L7QvdGE0LjQs9GD0YDQsNGG0LjQuCAx0KEt0LHQsNC3IHwgZW5hYmxlZFtmYTpmYS1mb2xkZXIgZW5hYmxlZF1cbiAgICBkZWYgLS0tIHwg0J7QsdGJ0LjQtSDQvdCw0YHRgtGA0L7QudC60Lgg0LrQvtC90YTQuNCz0YPRgNCw0YbQuNC5IDHQoS3QsdCw0LcgfCBkaXJlY3RvcnkuY29uZltmYTpmYS1maWxlIGRpcmVjdG9yeS5jb25mXVxuXG4gICAgYXZhaWxhYmxlID09PSB8INCk0LDQudC70Ysg0LrQvtC90YTQuNCz0YPRgNCw0YbQuNC5IDHQoS3QsdCw0LcgfCBmaWxlLmNvbmZbZmE6ZmEtZmlsZSAqLmNvbmZdXG4gICAgZW5hYmxlZCA9PT0gfCDQodGB0YvQu9C60Lgg0L3QsCDRhNCw0LnQu9GLINC60L7QvdGE0LjQs9GD0YDQsNGG0LjQuSAx0KEt0LHQsNC3IHwgbGluay5jb25mW2ZhOmZhLWxpbmsgKi5jb25mXVxuICAgIFxuICAgIGxpbmsuY29uZiAtLi0-IHwg0JLQutC7L9CS0YvQutC7INGBINC_0L7QvNC-0YnRjNGOINGB0YHRi9C70LrQuCB8IGZpbGUuY29uZlxuXG4gICAgdnJkID09PSB8INCa0LDRgtCw0LvQvtCz0Lgg0LrQu9C40L3RgtC-0LIg0LHQvtC10LLQvtC5IDHQoS3QsdCw0LfRiyB8IHByb2RbZmE6ZmEtZm9sZGVyICoucHJvZF1cbiAgICBwcm9kIC0tLSB8INCa0LDRgtCw0LvQvtCzINC60LvQuNC10L3RgtCwIDHQoS3QsdCw0LfRiyDRgNCw0LfRgNCw0LHQvtGC0LrQuCB8IGRldltmYTpmYS1mb2xkZXIgZGV2XVxuICAgIFxuICAgIHByb2QgLS0tIHwg0J3QsNGB0YLRgNC-0LnQutCwINC60LvQuNC10L3RgtCwINCx0L7QtdCy0L7QuSAx0KEt0LHQsNC30YsgfCBwcm9kLnZyZFtmYTpmYS1maWxlIHByb2QudnJkXVxuICAgIGRldiAtLS0gfCDQndCw0YHRgtGA0L7QudC60LAg0LrQu9C40LXQvdGC0LAgMdChLdCx0LDQt9GLINGA0LDQt9GA0LDQsdC-0YLQutC4IHwgZGV2LnZyZFtmYTpmYS1maWxlIGRldi52cmRdXG4gICAgXG4gICAgZGVmLmNvbmYgLS0-IGxpbmsuY29uZlxuICAgIGZpbGUuY29uZiAtLT4gZGlyZWN0b3J5LmNvbmZcbiAgICBmaWxlLmNvbmYgLS0-IHByb2QudnJkXG4gICAgZmlsZS5jb25mIC0tPiBkZXYudnJkXG5cbiAgICBhcGFjaGUyW2ZhOmZhLWZvbGRlciAvZXRjL2FwYWNoZTJdXG4gICAgYXBhY2hlMiAtLS0gc2l0ZXMtYXZhaWxhYmxlW2ZhOmZhLWZvbGRlciBzaXRlcy1hdmFpbGFibGVdXG4gICAgYXBhY2hlMiAtLS0gbW9kcy1hdmFpbGFibGVbZmE6ZmEtZm9sZGVyIG1vZHMtYXZhaWxhYmxlXVxuXG4gICAgbW9kcy1hdmFpbGFibGUgLS0tIGxpbmsud3NhcDI0LmNvbmZbZmE6ZmEtbGluayB3c2FwMjQuY29uZl1cbiAgICBtb2RzLWF2YWlsYWJsZSAtLS0gbGluay53c2FwMjQubG9hZFtmYTpmYS1saW5rIHdzYXAyNC5sb2FkXVxuXG4gICAgbGluay53c2FwMjQuY29uZiAtLi4tPiB3c2FwMjQuY29uZlxuICAgIGxpbmsud3NhcDI0LmxvYWQgLS4uLT4gd3NhcDI0LmxvYWRcblxuICAgIHNpdGVzLWF2YWlsYWJsZSAtLS0gZXRjLmRlZi5jb25mW2ZhOmZhLWxpbmsgMDAwLWRlZmF1bHQuY29uZl1cbiAgICBldGMuZGVmLmNvbmYgLS4tPiBkZWYuY29uZlxuXG4gICAgZGlzdHJpYltmYTpmYS1mb2xkZXIgL2hvbWUvb2VtL2VzaW5hL2Rpc3RyaWJdID09PSB2ZXJzaW9uW2ZhOmZhLWZvbGRlciB2ZXJzaW9uL29wdC8xQy92OC4zL3g4Nl82NF1cbiAgICBwbGF0Zm9ybVtmYTpmYS1saW5rIC9ob21lL29lbS9lc2luYS9wbGF0Zm9ybV0gLS4tPiB2ZXJzaW9uXG5cbiAgICB3c2FwMjQubG9hZCAtLT4gcGxhdGZvcm0iLCJtZXJtYWlkIjoie1xuICBcInRoZW1lXCI6IFwiZGVmYXVsdFwiXG59IiwidXBkYXRlRWRpdG9yIjp0cnVlLCJhdXRvU3luYyI6dHJ1ZSwidXBkYXRlRGlhZ3JhbSI6ZmFsc2V9)
