# {{date}}

## 📸 現場
* 

---

## 🧠 インプット・アイデア（Web・動画・技術）
* 

---

## 💊ヘルスケア
- 体重：

---

## 📝 スケジュール・雑記

### 📅Googleカレンダー予定

<%*
const events = await app.plugins.getPlugin('ics').getEvents(moment(tp.file.title, "YYYY-MM-DD"));

if (!events || events.length === 0) {
    tR += `- 予定なし\n`;
} else {
    events.sort((a, b) => a.utime - b.utime).forEach((event) => {
        const { time, endTime, summary, icsName, callUrl, callType, location, attendees } = event;

        // Extract custom fields
        const videoCallURLs = event.extractedFields?.["Video Call URLs"] || [];

        // Format attendees
        const attendeeList = attendees
            ? attendees
                .filter(attendee => attendee.name || attendee.email)
                .map(attendee => {
                    const name = attendee.name || attendee.email;
                    const email = attendee.email || "";
                    return email ? `[${name}](mailto:${email})` : name;
                })
                .join(", ")
            : "";

        // Format location
        const hasLocation = location && location.trim().length > 0;
        const encodedLocation = hasLocation ? encodeURIComponent(location.trim()) : "";

        // Calendar name
        const calendarName = icsName ? ` ${icsName}` : "";

        // Main event line
        tR += `- [ ] ${time}-${endTime} **${summary}**${calendarName}\n`;

        // Add location and Google Maps link
        if (hasLocation) {
            tR += `    - 📍 ${location}\n`;
            tR += `    - 🗺️ [Google Mapsで開く](https://www.google.com/maps/search/?api=1&query=${encodedLocation})\n`;
        }

        // Add video call URL if present
        if (callUrl) {
            tR += `    - 🎥 [${callType || "Video Call"}](${callUrl})\n`;
        }

        // Add extracted video call URLs if present
        if (videoCallURLs.length > 0) {
            tR += `    - Video Call URLs:: ${videoCallURLs.join(", ")}\n`;
        }

        // Add attendees if present
        if (attendeeList) {
            tR += `    - Attendees:: ${attendeeList}\n`;
        }
    });
}
%>

---

### 雑記
* 

<!-- spotify-obsidian:daily:begin -->
## Spotifyログ

```dataviewjs
const noteDate = dv.current().file.name;
if (/^\d{4}-\d{2}-\d{2}$/.test(noteDate)) {
  const path = "Spotify/Spotifyログ/" + noteDate;
  const link = dv.fileLink(path, false, "Spotifyログを開く");
  dv.paragraph(link);
  if (dv.page(path)) {
    dv.paragraph(dv.sectionLink(path, "再生履歴", true));
  } else {
    dv.paragraph("再生履歴なし（ログ未生成。生成後は自動表示されます）");
  }
} else {
  dv.paragraph("Spotifyログ：ノート名をYYYY-MM-DD形式にしてください");
}
```
<!-- spotify-obsidian:daily:end -->
