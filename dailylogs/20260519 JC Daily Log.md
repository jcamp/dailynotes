## JC Daily log for 20260519

### Glance - The wonderful totally configurable Dashboard and RSS reader PLUS a lot more!

https://github.com/glanceapp/glance

If you do not have this installed - DO IT!

### Freemind - Free mindmapping tool - been around for donkeys years!

https://freemind.sourceforge.io/wiki/index.php/Main_Page

FreeMind is a free/open-source mind-mapping software written in Java. 
Many consider it to be a high productivity tool. 
We are proud that the operation and navigation of FreeMind is faster than that of MindManager because of one-click "fold / unfold" and "follow link" operations.

### Noted - All about self-hosting and searchable list of solutions

https://noted.lol/

What is Noted and how can we help you learn more about self-hosting and open-source software?

Noted is an independent publication that took its first steps in April 2022. 
Our main areas of interest orbit around Home Lab, Self Hosting, Security, and all things Open Source or free software, often referred to as FOSS.

### Youtube Channels to RSS Export file

https://github.com/jeb5/YouTube-Subscriptions-RSS

Use this script to get the RSS feeds of all your YouTube subscriptions. It downloads as an OPML file, which can be imported into your favorite RSS reader.
Gets the Channel ID's from channels which is very useful for RSS readers, etc.

Usage:  
Navigate to youtube.com/feed/channels.
Run the script or activate the bookmarklet. An OPML file will download, and a list of RSS feeds will be logged to the console if you need it.
Import into your favorite RSS reader, and let me know if you run into any issues.

Paste this into the console at youtube.com/feed/channels to download the OPML file:

```
(async () => {
   const dialog = document.createElement("dialog");
   const label = document.createElement("label");
   const progress = document.createElement("progress");
   dialog.style.cssText = "display: flex; flex-direction: column; gap: 15px; padding: 20px;";
   dialog.appendChild(label);
   dialog.appendChild(progress);
   document.querySelector("ytd-app").appendChild(dialog);
   dialog.showModal();
   label.innerText = "Loading subscriptions...";
   const content = document.getElementById("content");
   let contentH;
   do {
      contentH = content.offsetHeight;
      window.scrollBy(0, 100000);
      await new Promise((r) => setTimeout(r, 500));
   } while (content.querySelector("#spinnerContainer.active") != null || content.offsetHeight > contentH);
   try {
      const channelElements = [...content.querySelectorAll("ytd-browse:not([hidden]) #main-link.channel-link")];
      progress.max = channelElements.length;
      progress.value = 0;
      const channels = [];
      for (e of channelElements) {
         label.innerText = `Fetching URLS... (${progress.value}/${progress.max})`;
         try {
            const channelName = e.querySelector("yt-formatted-string.ytd-channel-name").innerText;
            const channelReq = await fetch(e.href);
            if (!channelReq.ok) {
               console.error(`Couldn't fetch channel page for ${channelName}`);
               continue;
            }
            let channelHTML = await channelReq.text();
            const rssUrlMatch = channelHTML.match(/<link\srel="alternate"\stype="application\/rss\+xml"\stitle="RSS"\shref="(.+?)"/);
            if (rssUrlMatch == null) {
               console.error(`Couldn't find RSS feed for ${channelName}`);
               continue;
            }
            channels.push([rssUrlMatch[1], channelName, e.href]);
         } finally {
            progress.value++;
            progress.replaceWith(progress);
         }
      }
      if (channelElements.length == 0) alert("Couldn't find any subscriptions");
      const missedChannels = channelElements.length - channels.length;
      if (missedChannels > 0)
         alert(`${missedChannels} channel${missedChannels > 1 ? "s" : ""} couldn't be fetched. Check the console for more info.`);
      const escapeXML = (str) =>
         str.replace(/[<>&'"]/g, (c) => ({ "<": "&lt;", ">": "&gt;", "&": "&amp;", "'": "&apos;", '"': "&quot;" }[c]));
      if (channels.length > 0) {
         console.log(channels.map(([feed]) => feed).join("\n"));
         let opmlText = `<?xml version="1.0" encoding="UTF-8"?>\n<opml version="1.0">\n\t<head>\n\t\t<title>YouTube Subscriptions as RSS</title>\n\t</head>\n\t<body>\n\t\t<outline text="YouTube Subscriptions">${channels
            .map(
               ([feed, channelName, channelUrl]) =>
                  `\n\t\t\t<outline type="rss" text="${escapeXML(channelName)}" title="${escapeXML(
                     channelName
                  )}" xmlUrl="${feed}" htmlUrl="${channelUrl}"/>`
            )
            .join("")}\n\t\t</outline>\n\t</body>\n</opml>`;
         const url = window.URL.createObjectURL(new Blob([opmlText], { type: "text/plain" }));
         const anchorTag = document.createElement("a");
         anchorTag.setAttribute("download", "youtube_subs.opml");
         anchorTag.setAttribute("href", url);
         anchorTag.dataset.downloadurl = `text/plain:youtube_subs.opml:${url}`;
         anchorTag.click();
      }
   } catch (e) {
      console.error(e);
      alert("Something went wrong. Check the console for more info.");
   } finally {
      dialog.close();
      dialog.remove();
   }
})();
```
