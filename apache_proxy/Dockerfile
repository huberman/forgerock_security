FROM httpd:2.4
#COPY index.html /usr/local/apache2/htdocs/
# this is a bit of a cheat as it copies a configured web agent rather than doing a full
# blank sheet configuration - sorry...
COPY opt/web_agents/apache24_agent/ /opt/web_agents/apache24_agent/
RUN echo LoadModule proxy_module modules/mod_proxy.so >> /usr/local/apache2/conf/httpd.conf
RUN echo LoadModule proxy_http_module modules/mod_proxy_http.so >> /usr/local/apache2/conf/httpd.conf
RUN echo ProxyPass / "\${UNDERLYING}" >> /usr/local/apache2/conf/httpd.conf
RUN echo ProxyPassReverse / "\${UNDERLYING}" >> /usr/local/apache2/conf/httpd.conf
RUN echo include /opt/web_agents/apache24_agent/Agent_003/config/dsame.conf >> /usr/local/apache2/conf/httpd.conf

