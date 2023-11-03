## Content of the contribution 

	- this readme presenting the context, nature of the contribution and list of extensions
	- the extension schema in json.	

## Context of the contribution 

The ever-increasing ease of disseminating, accessing, and now generating information, whether true or not, enables a wide range of actors today to conduct large-scale influence operations. Taking advantage of the economic model of the majority of content providers and hosters on the Internet, these actors are capable of destabilizing entire societies.

Identifying, categorizing these events and then sharing analyses between expert teams implies for them to speak a common language, to describe disinformation with a common model.

This need is very similar to what Cyber Threat Intelligence needs when analysing cyber attacks. And CTI has now STIX 2.1 data model combat-proven.

Filigran strongly believes DAD-CDM open project is a grat place to create a common language for all of those who fight against disinformation and that the project should use what have been done with STIX to gain several years of advance in this quest.

## Nature of the contribution

Filigran has been involved in several influence campaign modeling projects, notably in collaboration with EEAS and Viginum.
Leveraging its expertise in implementing the STIX 2.1 framework (link), this work led to an extension of STIX to cover essential needs in modeling disinformation campaigns.
This extension has been implemented in the data model of the OpenCTI platform and is operationally used by several teams of analysts specialized in fighting disinformation,; daily.
Within the OpenCTI platform, this extension is used in conjunction with the DISARM matrix and specialized vocabularies finetuned by analysts themselves to describe the types of observed events, narratives and so on.

If you want to know more, you can read the Filigran blogpost: https://medium.com/filigran/how-opencti-helps-to-fight-desinformation-and-foreign-interferences-424a3d02f2c7

List of extensions
- SDO Narrative: Narratives are the concepts and the discourse used by threat actors to carry out foreign interferences and manipulation campaigns.
	- Threat Actor/Campaign/Incident <uses> Narrative 
	- Channel/Tool <uses> Narrative 
	- Narrative <subnarrative-of> Narrative 
- SCO Media Content: Modelization of a media content such as a tweet, a blog post, and so on.
	- Channel <publishes> Media-Content
	- Media-Content <language_refs> Language
- SDO Channel: Channels are any online or offline communication mean (a website, social media profile or page, TV station etc.).
	- Channel <uses> Tool
	- Channel <uses> Narrative 
	- Channel <uses> Attack Pattern 
	- Channel <amplifies> Channel 
	- Channel <belongs-to> Identity/Threat Actor/User-Account
	- Threat Actor/Campaign/Incident <uses> Channel
	- Channel <language_refs> Language
	- Channel <uses> Infrastructure
	- Channel <publishes> Url/Media Content
	- Channel <targets> Event/Identity/Location
- SDO Event: Events represent a real life event like an election, show, anniversary etc. to provide context in which incidents can take place.
	- Channel <targets> Event
	- Tool <targets> Event 
	- Threat Actor/Campaign/Incident <targets> Event
- SDO Language: Languages are the concepts and the discourse used by threat actors to carry out foreign interferences and manipulation campaigns.

