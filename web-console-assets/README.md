

```
oc new-app nginx:1.12~https://github.com/siamaksade/multi-cloud-cd-demo.git#v3.9 --name=assets --context-dir=web-console-assets -n openshift-web-console
```

OR

```
oc new-build --name=assets --image-stream=nginx:1.12 --binary -n openshift-web-console
oc new-app --name=assets -i assets -n openshift-web-console
oc create route edge assets --service=assets openshift-web-console
```

SVG Editor: https://www.vecteezy.com/editor


Edit `webconsole-config` config map:

```
extensions:
  stylesheetURLs:
    - https://example.com/custom-dev.css
```