Your answers to the questions go here.

--LEVEL 1--

-Bonus question: what is the agent?

The Agent is a program that will run on either a computer (as in my case) or throughout an entire system, monitoring customized metrics based on user preferences. The results of the ddagent are then sent back to datadog servers for storage and I assume historcal analysis. 

-Submit an event via the API

I used bash, here is how i proceded, I decided to use the example, excplicitly: 

1. First authenticated my API key

2. Then made my request: eugenes-MacBook-Air:.datadog-agent eugenewatson$ curl  -X POST -H "Content-type: application/json" \
> -d '{
>       "title": "Did you hear the news today?",
>       "text": "Oh boy!",
>       "priority": "normal",
>       "tags": ["environment:test"],
>       "alert_type": "info"
>   }' \
> 'https://app.datadoghq.com/api/v1/events?api_key=6b62475fc7a42cbb49b69a4db7d58ccc'

3. Then received a good response : {"status": "ok", "event": {"priority": "normal", "date_happened": 1405525120, "handle": null, "title": "Did you hear the news today?", "url": "https://app.datadoghq.com/event/jump_to?event_id=2369987361678926501", "text": "Oh boy!", "tags": ["environment:test"], "related_event_id": null, "id": 2369987361678926501}}

-Get event to appear in my email inbox


