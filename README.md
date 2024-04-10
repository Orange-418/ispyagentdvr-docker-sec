<h1>iSpy Agent DVR multi-arch with security as highest concern image</h1>
<img alt="ispyagentdvr" src="https://ispycontent.azureedge.net/img/ispy2.png">
<p> CREDIT CREDIT CREDIT: https://github.com/MekayelAnik/ispyagentdvr-docker </p>
<p> I mainly made this for personal use and convenience</p>
<p>This is an unofficial multi-aarch docker image of Agent DVR of iSpy created for multiplatform support. iSpy Agent DVR creates a local server for IP cameras to be managed. Official Website: <a href="https://www.ispyconnect.com" rel="nofollow noopener">https://www.ispyconnect.com</a>
</p>

<p>Here are some example snippets to help you get started creating a container.</p>
<h3>docker-compose (recommended, <a href="https://itnext.io/a-beginners-guide-to-deploying-a-docker-application-to-production-using-docker-compose-de1feccd2893" rel="nofollow noopener">click here for more info</a>) </h3>
<pre><code>---
services:
  ispyagentdvr:
    build: ispyagentdvr-docker/latest-image-builder
    container_name: ispyagentdvr
    environment:
      - WEBUI_PORT=8090
      - TZ=America/Chicago
    volumes:
      - /AgentDVR/Media/XML:/AgentDVR/Media/XML
      - /AgentDVR/Media/WebServerRoot/Media:/AgentDVR/Media/WebServerRoot/Media
      - /AgentDVR/Commands:/AgentDVR/Commands
    user: '1006:1006'
    security_opt:
      - no-new-privileges:true
    cap_drop:
      - ALL
    networks:
      - agentdvr
    ports:
      - 8090:8090
      - 3478:3478/udp
      - 50000-50010:50000-50010/udp
    restart: unless-stopped
networks:
  agentdvr:
    external: true

</code></pre>


<h2>Issues & Requests</h2>
<p> To submit this Docker image specific issues or requests visit this docker image's Github Link: <a href="https://www.github.com/MekayelAnik/ispyagentdvr-docker" rel="nofollow noopener">https://www.github.com/MekayelAnik/ispyagentdvr-docker</a>
</p>
<p> For iSpy AgentDVR related issues and requests, please visit: <a href="https://www.reddit.com/r/ispyconnect/" rel="nofollow noopener">https://www.reddit.com/r/ispyconnect/</a>
</p>
