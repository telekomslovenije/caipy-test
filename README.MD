In replay.html, you need to change the following API end points ... 

	// remote API endpoints
	var caipyChannelListAPI = 'http://CHANNEL_LIST_API/caipy_channels/';
	var channelEventsAPI = 'http://CHANNEL_EVENTS_API/events/{channelID}/';

CaipyChannelListAPI should return json with the channel list id's that are used 
for retrieving epg events ... 

	{
		"caipy_channels": [{
			"epg_sd": "TEST",
			"epg_hd": "TESTHD",
			"epg_4k": null
		},
		{
			"epg_sd": "KIND",
			"epg_hd": "KINDHD",
			"epg_4k": null
		}]
	}

And ChannelEventsAPI output is also json that contains list of events with infos
about title, event id, end and start timestamps and also vbegin and vend for stream positions


	{
		"events": [{
			"url_info": {
				"vend": 109483200,
				"vbegin": 109466400
			},
			"title": "Glasbeni mikser",
			"event_id": 29630588,
			"end": "2017-06-21T06:00:00+02:00",
			"start": "2017-06-21T01:20:00+02:00"
		}]
	}

You also need to replace streaming urls (currently supporting Unified Streaming out of the box):

var originalStream = "http://ADAPTIVE_STREAMING_CDN/" + channelName + "/" + channelName + ".isml/" + channelName + ".m3u8?vbegin=" + start + "&vend=" + end;