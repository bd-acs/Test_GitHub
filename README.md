# Test_GitHub
You can also check the list of most recently delivered events by Github by going to Organization → Settings → Webhooks and clicking on the webhook you are interested in and there will be a Recent Deliveries section where you can see all the events. 

Things to note: if something were to fail on local and it responds a 4xx on the terminal from localhost, you might not see 4xx on GitHub in the recent deliveries section. This is mainly because from Github perspective, it successfully delivered the payload to smee and got a response from smee.

The HTTP status that you see on the terminal is the true value that will be in Github recent deliveries when we test this whole workflow from dev/staging/ production environment. 

We need to still evaluate if there is a way to send the response from local back to smee and in turn back to Github. However, this is not a priority item since we have most of the infra & setup ready based on the above steps that will enable us with local development, debugging & testing.

acs@BD-MB30008 ~ % smee -u https://smee.io/95a8296b-b1b4-4210-835e-135f8bcb5787 -t http://127.0.0.1:8080/webhooks/github_standard/95a8296b-b1b4-4210-835e-135f8bcb5787
Connected to https://smee.io/95a8296b-b1b4-4210-835e-135f8bcb5787
Forwarding https://smee.io/95a8296b-b1b4-4210-835e-135f8bcb5787 to http://127.0.0.1:8080/webhooks/github_standard/95a8296b-b1b4-4210-835e-135f8bcb5787

smee -u https://smee.io/95a8296b-b1b4-4210-835e-135f8bcb5787 -t http://127.0.0.1:8080/events/github/github_standard/95a8296b-b1b4-4210-835e-135f8bcb5787
