                   
                   
┌─────────────────┐
│ 4 Code Findings │
└─────────────────┘
                       
    deployment-dvwa.yml
    ❯❱ yaml.kubernetes.security.allow-privilege-escalation-no-securitycontext.allow-privilege-escalation-no-
       securitycontext                                                                                      
          In Kubernetes, each pod runs in its own isolated environment with its own set of security policies. 
          However, certain container images may contain `setuid` or `setgid` binaries that could allow an     
          attacker to perform privilege escalation and gain access to sensitive resources. To mitigate this   
          risk, it's recommended to add a `securityContext` to the container in the pod, with the parameter   
          `allowPrivilegeEscalation` set to `false`. This will prevent the container from running any         
          privileged processes and limit the impact of any potential attacks. By adding a `securityContext` to
          your Kubernetes pod, you can help to ensure that your containerized applications are more secure and
          less vulnerable to privilege escalation attacks.                                                    
          Details: https://sg.run/eleR                                                                        
                                                                                                              
           ▶▶┆ Autofix ▶ securityContext: allowPrivilegeEscalation: false name
           35┆ - name: dvwa
                        
    deployment-mysql.yml
    ❯❱ yaml.kubernetes.security.allow-privilege-escalation-no-securitycontext.allow-privilege-escalation-no-
       securitycontext                                                                                      
          In Kubernetes, each pod runs in its own isolated environment with its own set of security policies. 
          However, certain container images may contain `setuid` or `setgid` binaries that could allow an     
          attacker to perform privilege escalation and gain access to sensitive resources. To mitigate this   
          risk, it's recommended to add a `securityContext` to the container in the pod, with the parameter   
          `allowPrivilegeEscalation` set to `false`. This will prevent the container from running any         
          privileged processes and limit the impact of any potential attacks. By adding a `securityContext` to
          your Kubernetes pod, you can help to ensure that your containerized applications are more secure and
          less vulnerable to privilege escalation attacks.                                                    
          Details: https://sg.run/eleR                                                                        
                                                                                                              
           ▶▶┆ Autofix ▶ securityContext: allowPrivilegeEscalation: false name
           35┆ - name: mysql
              
    secret.yml
    ❯❱ yaml.kubernetes.security.secrets-in-config-file.secrets-in-config-file
          Secrets (czNyMDB0cGE1NQ==) should not be stored in infrastructure as code files. Use an alternative
          such as Bitnami Sealed Secrets or KSOPS to encrypt Kubernetes Secrets.                             
          Details: https://sg.run/KyL6                                                                       
                                                                                                             
            8┆ ROOT_PASSWORD: czNyMDB0cGE1NQ==
            ⋮┆----------------------------------------
    ❯❱ yaml.kubernetes.security.secrets-in-config-file.secrets-in-config-file
          Secrets (cEBzc3dvcmQ=) should not be stored in infrastructure as code files. Use an alternative such
          as Bitnami Sealed Secrets or KSOPS to encrypt Kubernetes Secrets.                                   
          Details: https://sg.run/KyL6                                                                        
                                                                                                              
           10┆ DVWA_PASSWORD: cEBzc3dvcmQ=
