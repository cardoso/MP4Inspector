# MP4Inspector
<img src="https://us-central1-trackgit-analytics.cloudfunctions.net/token/ping/l2q8nl1mv69fkeim79rl" alt="trackgit-views" />

A chrome extension to help you inspect Mp4 content and find irregularities in streams.

# Installation

- In chrome navigate to chrome://extensions/ (edge://extensions/ for chromium edge)
- Enable developer mode
- Click `Load unpacked extension`
- Select the folder where you cloned this into

# Usage

After installation the Mp4Inspector should show up as a new tab in your DevTools.

## Filter Results
In order to narrow down the elements on the network column, there are two filter methods available [File name](#filter-by-url) and [box name](#filter-by-mp4-box). They can also be combined to only show entries which match both filter entries.

### Filter by URL
Filters all entries to only show entries which have their URL partially matching the entered value.
![Filter by URL part](/readmeResources/UrlSearch.gif)

### Filter by Mp4 Box
Filters all entries to only show entries which contain a box with the exact value in the search field.
![Filter by URL part](/readmeResources/BoxSearch.gif)

## Comparison View

This view lets you compare the boxes of two segments.
You can open it by selecting any two segments and pressing the compare button 
![compareViewButton](/readmeResources/compareViewButton.png)

The results will be color coded meaning:
```diff
+ Green for boxes which are the same in both segments
- Red for boxes / values which are different
! Orange for boxes which only exist in one of the segments
```

![Comparison view in action](/readmeResources/CompareView.gif)

## Download segments
For more detailed inspection (eg: FFProbe or crafting a test asset), the MP4Inspector offers the possibility to download segments. You can select one or multiple entries in the network column and click the download button. A download will be started for each selected entry, but Chrome will only allow 10 downloads at a time.

There is also the possiblity to concatenate segments, which can be used to create a playable part of the asset by combining the init segment with any number of data segments. Currently muxing is not supported, so you have to ensure that only audio or video segments are selected.

![Download possibilities](/readmeResources/download.gif)
