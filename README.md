# sso test 20190816105500

First attempt to try out Oauth2 via Spring. Application.yml was intentionally not checked in. Do note that the pom.xml version for the various libraries
are very important for SSO to work.


security:  
  oauth2: 
    issuer: https://<okta-developer>/oauth2/default  
    client:  
      # From OIDC app  
      clientId: <client_id>  
      clientSecret: <client_secret>   
      # From Authorization Server's metadata  
      accessTokenUri: https://<okta-developer>/oauth2/default/v1/token   
      userAuthorizationUri: https://<okta-developer>/oauth2/default/v1/authorize   
      clientAuthenticationScheme: form   
      scope: openid profile email  
    resource:    
      # from your Auth Server's metadata, check .well-known/openid-configuration if not in .well-known/oauth-authorization-server.   
      userInfoUri: https://<okta-developer>/oauth2/default/v1/userinfo
  
