In replay.html, you need to change the following API end points ... 

	// remote API endpoints
var caipyChannelListAPI = 'http://vidra-apid.siol.tv/api/caipy_test/caipy_channels/';
var channelEventsAPI = 'http://vidra-apid.siol.tv/api/caipy_test/events/{channelID}/';

CaipyChannelListAPI should return json with the channel list id's that are used 
for retrieving epg events ... 

{
"caipy_channels": [
{
"epg_sd": "TEST",
"epg_hd": "TESTHD",
"epg_4k": null
},
{
"epg_sd": "KIND",
"epg_hd": "KINDHD",
"epg_4k": null
}
]}

And ChannelEventsAPI output is also json that contains list of events with infos
about title, event id, end and start timestamps and also vbegin and vend for stream positions


{
"events": [
{
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