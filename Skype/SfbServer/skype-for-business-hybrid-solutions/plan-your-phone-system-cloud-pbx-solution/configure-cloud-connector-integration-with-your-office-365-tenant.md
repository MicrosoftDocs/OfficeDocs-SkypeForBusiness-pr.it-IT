---
title: Configurare l'integrazione del connettore cloud con Microsoft 365 o Office 365 organizzazione
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Informazioni su come configurare l'integrazione di Cloud Connector con l'Microsoft 365 o Office 365 organizzazione.
ms.openlocfilehash: b3b8b13669a2e52ed5146e1bd0ca179a5542e43d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733375"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configurare l'integrazione del connettore cloud con Microsoft 365 o Office 365 organizzazione

> [!Important] 
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Informazioni su come configurare l'integrazione di Cloud Connector con l'Microsoft 365 o Office 365 organizzazione.
  
Al termine dell Skype for Business Cloud Connector Edition installazione, eseguire i passaggi descritti in questa sezione per configurare la distribuzione e connetterla all'Microsoft 365 o Office 365 organizzazione.
  
## <a name="configure-firewall-settings"></a>Configurare le impostazioni del firewall

Configurare le impostazioni del firewall per le impostazioni del firewall interno ed esterno per la rete perimetrale in modo da aprire le porte necessarie, come descritto in [Porte](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) e protocolli in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurare i gateway PSTN (Public Switched Telephone Network)

Configurare i trunk in ogni gateway PSTN in modo che puntino a Mediation Server per tutte le appliance. Poiché il nome di dominio completo del pool è lo stesso per tutti i server del pool, ogni trunk deve puntare a un FQDN o a un indirizzo IP di Mediation Server anziché all'FQDN del pool Mediation Server. I trunk devono essere impostati con la stessa priorità.
  
Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e i Mediation Server per supportare MTLS nel modo seguente:
  
1. Esportare la CA radice dal computer Active Directory di Cloud Connector.
    
2. Seguire le istruzioni del fornitore del gateway PSTN per importare la CA radice.
    
3. Importare il certificato della CA radice per il certificato emesso nel gateway nei Mediation Server. Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio Autorità di certificazione in esecuzione nel computer Cloud Connector Active Directory come indicato di seguito:
    
   - Modificare il modello di server Web esistente per consentire agli utenti autenticati di eseguire la registrazione o creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione. Per istruzioni dettagliate, vedere [Certificate Templates.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - Richiedere un certificato utilizzando lo snap-in Certificato selezionando il modello server Web abilitato. Assicurarsi di aggiungere Nome comune in Oggetto e Nome DNS in Nome alternativo con FQDN del gateway e verificare che nella chiave privata che rendi esportabile la chiave privata sia selezionata in Opzioni chiave. 
    
4. Esportare il certificato SSL con chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.
    
## <a name="update-the-domain-for-your-tenant"></a>Aggiornare il dominio per il tenant

Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-for-your-edge"></a>Aggiungere record DNS per edge

Aggiungere i record DNS seguenti all'Microsoft 365 o Office 365'organizzazione. Per informazioni su come aggiungere record DNS, vedere [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Aggiungere un record A DNS per Access Edge.
    
2. I record SRV verranno creati automaticamente da Microsoft 365 o Office 365 e dagli script di distribuzione. Verificare che sia possibile cercare i due servizi SIP seguenti nell'edge: \_ sip e \_ sipfederationtls.
    
     ![Conferma record SRV.](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Configurare la connettività ibrida tra Cloud Connector Edition e Microsoft 365 o Office 365

Per configurare la connettività ibrida tra la distribuzione Skype for Business Cloud Connector Edition e l'organizzazione Microsoft 365 o Office 365, eseguire il cmdlet seguente in una sessione remota di PowerShell. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [Configurare il computer per Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
Il cmdlet imposta il nome di dominio completo esterno di Access Edge. Nel primo dei comandi, deve essere quello per \<External Access Edge FQDN\> il ruolo Sip Access Edge. Per impostazione predefinita, deve essere \<Domain Name\> ap.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> L'FQDN di Access Edge esterno utilizzato per la destinazione peer deve essere impostato su un sito PSTN che verrà utilizzato solo come fallback nel caso in cui un utente non sia assegnato a un sito PSTN. Per ulteriori informazioni, vedere [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e Deploy multiple sites in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
## <a name="set-up-pstn-gateways"></a>Configurare i gateway PSTN

Configurare i trunk in ogni gateway PSTN in modo che puntino a Mediation Server per tutte le appliance. Ogni trunk deve puntare a un FQDN o a un indirizzo IP di Mediation Server anziché all'FQDN del pool Mediation Server perché l'FQDN del pool è lo stesso per tutti i server del pool. I trunk devono essere impostati con la stessa priorità.
  
Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e i Mediation Server per supportare MTLS nel modo seguente:
  
1. Esportare la CA radice dal computer Active Directory di Cloud Connector.
    
2. Seguire le istruzioni del fornitore del gateway PSTN per importare la CA radice.
    
3. Importare il certificato della CA radice per il certificato emesso nel gateway nei Mediation Server. Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio Autorità di certificazione in esecuzione nel computer Cloud Connector Active Directory come indicato di seguito:
    
   - Modificare il modello di server Web esistente per consentire agli utenti autenticati di registrare o creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione. Per istruzioni dettagliate, vedere [Certificate Templates.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - Richiedere un certificato utilizzando lo snap-in Certificato selezionando il modello server Web abilitato. Assicurarsi di aggiungere Nome comune in Oggetto e Nome DNS in Nome alternativo con FQDN del gateway e verificare che nella chiave privata che rendi esportabile la chiave privata sia selezionata in Opzioni chiave. 
    
4. Esportare il certificato SSL con chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.
    
5. I gateway PSTN in un sito PSTN devono connettersi solo ai Mediation Server nello stesso sito.
    
## <a name="set-up-your-users"></a>Configurare gli utenti

Accedi al interfaccia di amministrazione di Microsoft 365, aggiungi gli utenti che saranno abilitati per i servizi vocali online e assegna una licenza E5 o un componente aggiuntivo Sistema telefonico alla licenza E3 a questi utenti. Per informazioni sull'aggiunta di utenti, vedere [Add users to Microsoft 365 for business.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Abilitare gli utenti per Sistema telefonico di segreteria telefonica e vocale
 
Dopo aver aggiunto gli utenti a Microsoft 365 o Office 365, abilitare i propri account per i Sistema telefonico vocali, inclusa la segreteria telefonica. Per abilitare queste funzionalità, è necessario accedere all'organizzazione di Microsoft 365 o Office 365 con un account che sia un ruolo amministratore globale ed essere in grado di eseguire PowerShell remoto. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [Configurare il computer per Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- Assegnare il criterio all'utente e configurare il numero di telefono vocale aziendale dell'utente, specificato con il valore del **parametro Identity:**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Un'identità utente può essere specificata utilizzando l'indirizzo SIP dell'utente, il nome dell'entità utente (UPN) o il nome visualizzato di Active Directory dell'utente (ad esempio, "Bob Kelly"). Il carattere asterisco ( \* ) può essere utilizzato anche con il nome visualizzato come identità dell'utente. Ad esempio, l'identità "Smith" restituisce tutti gli utenti con un nome visualizzato che termina con il valore \* stringa "Smith".
  
È quindi possibile verificare che gli utenti siano stati aggiunti e abilitati utilizzando lo script seguente:
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

Dovrai decidere se gli utenti devono essere in grado di effettuare chiamate internazionali. Per impostazione predefinita, le chiamate internazionali sono abilitate. È possibile disabilitare o abilitare gli utenti per la composizione internazionale tramite l'interfaccia di amministrazione Skype for Business online.
  
Per disabilitare le chiamate internazionali per utente, eseguire il cmdlet seguente in Skype for Business PowerShell online:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Per abilitare di nuovo le chiamate internazionali in base all'utente dopo che è stata disabilitata, eseguire lo stesso cmdlet, ma modificare il valore di **PolicyName** in *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Assegnare utenti a siti PSTN

Usare PowerShell remoto tenant per assegnare un sito agli utenti anche se è stato distribuito un solo sito. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [Configurare il computer per Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Se a un utente non è assegnato alcun sito PSTN, la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e l'organizzazione di Microsoft 365 o Office 365 verrà eseguito il fall back per utilizzare il livello di tenant predefinito 1 (Destinazione peer) in modo che le chiamate possano essere completate. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurare Impostazioni Mediation Server ibrido online
<a name="BKMK_ConfigureMediationServer"> </a>

Quando una chiamata P2P viene inoltrata a una conferenza PSTN, il server per conferenze di Skype for Business Online invierà un invito al Mediation Server cloud Connector. Per assicurarsi che Microsoft 365 o Office 365 instradare correttamente l'invito, è necessario configurare un'impostazione nel tenant online per ogni Mediation Server cloud Connector come segue: 
  
1. Creare un utente nella interfaccia di amministrazione di Microsoft 365. Utilizzare il nome utente desiderato, ad esempio "MediationServer1".
    
    Utilizzare il dominio SIP predefinito di Cloud Connector (il primo dominio SIP nel file .ini) come dominio utente.
    
    Tenere presente che l'assegnazione della licenza è necessaria solo per la propagazione dell'utente nella directory Skype for Business online. Assegnare una licenza Microsoft 365 o Office 365 (ad esempio E5) all'account creato, consentire fino a un'ora per la propagazione delle modifiche, verificare che il provisioning degli account utente sia stato eseguito correttamente nella directory online di Skype for Business eseguendo il cmdlet seguente, quindi rimuovere la licenza da questo account.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Avviare una sessione remota di PowerShell di Azure AD tenant usando le credenziali globali o di amministratore utente, quindi eseguire il cmdlet seguente per impostare il reparto per l'account utente di Azure AD configurato nel passaggio 1 su "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Avviare una sessione remota di PowerShell del tenant Skype for Business utilizzando le credenziali di amministratore tenant di Skype for Business, quindi eseguire il cmdlet seguente per impostare il mediation server e il nome di dominio completo del server perimetrale su tale account utente, sostituendo con il nome visualizzato dell'utente per l'account creato \<DisplayName\> nel passaggio 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Per Identità, utilizzare il nome visualizzato dell'account utente creato per questo Mediation Server.
    
    Per  *MediationServerFQDN,*  utilizzare il nome di dominio completo interno definito per il Mediation Server.
    
    Per  *EdgeServerExternalFQDN,*  utilizzare il nome di dominio completo esterno definito per il proxy di accesso al server perimetrale. Se sono presenti più siti PSTN del connettore cloud, scegliere l'FQDN del proxy di accesso al server perimetrale assegnato al sito in cui si trova il Mediation Server.
    
4. Se sono presenti più Mediation Server cloud Connector (più siti, ha), ripetere i passaggi precedenti per ognuno di essi.
