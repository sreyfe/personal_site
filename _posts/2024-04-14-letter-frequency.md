---
layout: post
title: Letter frequency by verse in Genesis
date: 2024-04-15 10:50:00
description: a brief look at letter frequency in Genesis
tags: 
categories: 
---

The other morning, still half-asleep, addled by a recent interest in the Masora and participation in the very interesting [DHJewish conference](https://www.mmz-potsdam.de/aktuelles/veranstaltungen/2024/the-value-of-the-digital-dhjewish-conference-and-hackathon) in Potsdam, I thought to myself: "you know, there's been a lot said about the Hebrew Bible beginning with ב and not with א, but aren't there a lot of א's in Genesis 1:1 anyway? There's one in every word except השמים... Maybe Genesis 1:1 is actually the verse in Genesis with the highest frequency of א..."

In order to check this, I took the unvocalized text of Genesis from Sefaria. For each verse, I divided the occurence of each letter by the total number of letters in the verse (treating final and non-final as the same letter). This gave me a measure of frequency, which I then ranked.

So, is Genesis 1:1 the verse with the highest frequency of א? Nope, it's in 13th place. Nonetheless, this little investigation turned up some interesting patterns. With the caveats that modern verse divisions are a pretty late addition, and short verses are over-represented, here are some of the more interesting ones:

- ג and ד are most frequent in the same verse: 49:19, wherein Jacob gives a prophecy for his son Gad (גד), punning repeatedly on his name.

- four out of five of the top-five verses for י are in Genesis 1. We can attribute this at least partly to the formulaic ויהי ערב ויהי בקר and the yuddiness of ordinal numbers (חמישי, רביעי). But 1:6, which is in 5th place, has neither ויהי ערב ויהי בקר nor ordinal numbers. Neither does 1:8, which is in 6th place... Perhaps the frequency of י here can be attributed to all the jussives, plus the repeated presence of "elohim?" Considering the importance of י, this one's a little spooky... It would be interesting to see if Genesis 1 was the chapter with the highest י frequency. A task for another day...

- the top-four verses in terms of פ-frequency are all from Genesis 36, owing to the repetition of אלוף.

- The verse with the highest frequency of ט has a frequency of only 0.060606 (36:22), the lowest of any letter. ז follows with 0.062500 (25:29). The letter with the highest frequency in a single verse is י, with 1:23 and 1:19 both having a frequency of 0.318181.

Below is a table indicating the verse with the highest frequency of a single letter. For a JSON with all this data, see the counts.json file [in this repo](https://github.com/sreyfe/hebrew_bible_frequencies).

| Letter | Verse (Genesis) | Text | Frequency |
| ------: | ------------ | ----: | ------------- |
|א|10:28|ואת עובל ואת אבימאל ואת שבא|0.272727|
|ב|43:1|והרעב כבד בארץ|0.250000|
|ג|49:19|גד גדוד יגודנו והוא יגד עקב|0.181818|
|ד|49:19|גד גדוד יגודנו והוא יגד עקב|0.227273|
|ה|7:8|מן הבהמה הטהורה ומן הבהמה אשר איננה טהרה ומן העוף וכל אשר רמש על האדמה|0.267857|
|ו (tie)|8:18|ויצא נח ובניו ואשתו ונשי בניו אתו|0.296296|
|ו (tie)|46:13|ובני יששכר תולע ופוה ויוב ושמרון|0.296296|
|ז|25:29|ויזד יעקב נזיד ויבא עשו מן השדה והוא עיף|0.062500|
|ח|5:21|ויחי חנוך חמש וששים שנה ויולד את מתושלח|0.125000|
|ט|36:22|ויהיו בני לוטן חרי והימם ואחות לוטן תמנע|0.060606|
|י (tie)|1:23|ויהי ערב ויהי בקר יום חמישי|0.318181|
|י (tie)|1:19|ויהי ערב ויהי בקר יום רביעי|0.318181|
|כ|34:15|אך בזאת נאות לכם אם תהיו כמנו להמל לכם כל זכר|0.171429|
|ל|6:21|ואתה קח לך מכל מאכל אשר יאכל ואספת אליך והיה|0.195652|
|מ|25:14|ומשמע ודומה ומשא|0.285714|
|נ|9:14|והיה בענני ענן על הארץ ונראתה הקשת בענן|0.218750|
|ס|12:9|ויסע אברם הלוך ונסוע הנגבה|0.090909|
|ע|44:33|ועתה ישב נא עבדך תחת הנער עבד לאדני והנער יעל|0.166667|
|פ|36:41|אלוף אהליבמה אלוף אלה אלוף פינן|0.153846|
|צ|19:23|השמש יצא על הארץ ולוט בא צערה|0.130435|
|ק|15:19|את הקיני ואת הקנזי ואת הקדמני|0.125000|
|ר (tie)|9:7|ואתם פרו ורבו שרצו בארץ ורבו בה|0.200000|
|ר (tie)|14:6|ואת החרי בהררם שעיר עד איל פארן אשר על המדבר|0.200000|
|ש|5:23|ויהי כל ימי חנוך חמש וששים שנה ושלש מאות שנה|0.200000|
|ת|34:9|והתחתנו אתנו בנתיכם תתנו לנו ואת בנתינו תקחו לכם|0.225000|