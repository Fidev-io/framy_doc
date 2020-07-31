# YAML configurations

> You can customize your Framy app in `yaml` file.

In `pubspec.yaml` or `framy.yaml` put configuration options under `framy` key.  

Current default configuration:
```yaml
framy:
  wrap-with-center: false
  wrap-with-safearea: false
  wrap-with-scaffold: true
  wrap-with-devicepreview: true
  show-material-components: true
  show-storyboard: true
```

See examples in [Counter App](https://github.com/Fidev-io/framy/blob/master/test_apps/counter_app/pubspec.yaml#L24-L26) or [WeightTracker](https://github.com/Fidev-io/framy/blob/master/test_apps/weight_tracker/framy.yaml).