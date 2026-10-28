# Data for Weather history

The gridded climate layers for the Weather history map
([mkerrn/lyn](https://github.com/mkerrn/lyn)), served by GitHub Pages from
`https://mkerrn.github.io/weatherdata/wx/`. They are kept here, not in the map's
repository, because all the years come to several hundred MB.

`wx/<layer>-<area>-<year>.bin.gz` holds one year and `-mean` the mean over
2016–2025, in the `WXG1` format described in the map's README. The map's
`data/wx/index.json` lists them. They are built by `fetch_climate.py` in the
map's repository, which writes straight into `wx/` here when this repository
is cloned next to it.

Source: MET Nordic analysis © Meteorologisk institutt (MET Norway), CC BY 4.0.

When the files are rebuilt, replace the history rather than adding to it, so
the repository stays small:

```
git checkout --orphan new && git add -A && git commit -m "data" &&
git branch -D main && git branch -m main && git push -f origin main
```
