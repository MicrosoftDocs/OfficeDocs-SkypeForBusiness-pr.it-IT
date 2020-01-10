---
title: Configurare l'integrazione Cloud Connector con il tenant di Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Informazioni su come configurare l'integrazione con il Cloud Connector con il tenant di Office 365.
ms.openlocfilehash: ed9437026ddbae07aadbe81585886ed0cb5cb0cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002856"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configurare l'integrazione Cloud Connector con il tenant di Office 365
 
Informazioni su come configurare l'integrazione con il Cloud Connector con il tenant di Office 365.
  
Una volta completata l'installazione di Skype for Business Cloud Connector Edition, eseguire i passaggi descritti in questa sezione per configurare la distribuzione e connetterla al tenant di Office 365.
  
## <a name="configure-firewall-settings"></a>Configurare le impostazioni del firewall

Configurare le impostazioni del firewall per le impostazioni del firewall interno ed esterno per la rete perimetrale per aprire le porte necessarie come descritto in [porte e protocolli](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurare i gateway PSTN (Public Switched Telephone Network)

Configurare Trunks in ogni gateway PSTN per puntare di nuovo a Mediation Server per tutti gli elettrodomestici. Poiché il nome di dominio completo del pool è lo stesso per tutti i server del pool, ogni trunk deve puntare a un nome di dominio completo di Mediation Server o indirizzo IP anziché il nome di dominio completo del pool di Mediation Server. I trunk devono essere impostati nella stessa priorità.
  
Se si usa TLS tra i server di mediazione e i gateway, sarà necessario configurare i gateway e i server di mediazione per supportare MTLS nel modo seguente:
  
1. Esportare la CA radice dal computer Active Directory Cloud Connector.
    
2. Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.
    
3. Importare il certificato della CA radice per il certificato emesso nel gateway in Mediation Servers. Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione usando il servizio autorità di certificazione in uso nel computer Active Directory Cloud Connector, come indicato di seguito:
    
   - Modificare il modello di server Web esistente per consentire agli utenti autenticati di eseguire la registrazione oppure creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione. Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
   - Richiedere un certificato usando lo snap-in certificato selezionando il modello di server Web abilitato. Assicurarsi di aggiungere il nome comune in nome oggetto e DNS in nome alternativo con FQDN del gateway e verificare che nella chiave privata sia selezionata l'opzione Imposta chiave privata esportabile in opzioni chiave. 
    
4. Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.
    
## <a name="update-the-domain-for-your-tenant"></a>Aggiornare il dominio per il tenant

Verificare di aver completato i passaggi per aggiornare il dominio in Office 365 e avere la possibilità di aggiungere record DNS. Per altre informazioni su come configurare il dominio in Office 365, vedere [aggiungere un dominio a office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Aggiungere record DNS in Office 365 per il proprio Edge

Aggiungere i record DNS seguenti al tenant di Office 365. Per informazioni su come aggiungere record DNS al tenant di Office 365, vedere [aggiungere o modificare record DNS personalizzati in office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Aggiungere un record DNS per Edge Access.
    
2. I record SRV verranno creati automaticamente da Office 365 e dagli script di distribuzione. Verificare che sia possibile cercare i due servizi SIP seguenti in Edge: _sip e _sipfederationtls.
    
     ![Conferma di record SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configurare la connettività ibrida tra Cloud Connector Edition e Office 365

Per configurare la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e il tenant di Office 365, eseguire il cmdlet seguente in una sessione remota di PowerShell. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
Il cmdlet imposta il nome di dominio completo esterno di Access Edge. Nel primo dei comandi l' \<FQDN\> del bordo di accesso esterno deve essere quello per il ruolo di Access Edge SIP. Per impostazione predefinita, questo deve essere il\<nome\>di AP. Domain.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> L'FQDN del bordo di accesso esterno usato per la destinazione peer deve essere impostato su un sito PSTN che verrà usato solo come fallback, se un utente non viene assegnato a un sito PSTN. Per altre informazioni, vedere [distribuire un singolo sito nel Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [distribuire più siti in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurare gateway PSTN

Configurare Trunks in ogni gateway PSTN per puntare di nuovo a Mediation Server per tutti gli elettrodomestici. Ogni trunk deve puntare a un FQDN di Mediation Server o a un indirizzo IP anziché al nome di dominio completo del pool di Mediation Server, perché il nome di dominio completo del pool è uguale per tutti i server del pool. I trunk devono essere impostati nella stessa priorità.
  
Se si usa TLS tra i server di mediazione e i gateway, sarà necessario configurare i gateway e i server di mediazione per supportare MTLS nel modo seguente:
  
1. Esportare la CA radice dal computer Active Directory Cloud Connector.
    
2. Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.
    
3. Importare il certificato della CA radice per il certificato emesso nel gateway in Mediation Servers. Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione usando il servizio autorità di certificazione in uso nel computer Active Directory Cloud Connector, come indicato di seguito:
    
   - Modificare il modello di server Web esistente per consentire agli utenti autenticati di eseguire la registrazione oppure creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione. Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Richiedere un certificato usando lo snap-in certificato selezionando il modello di server Web abilitato. Assicurarsi di aggiungere il nome comune in nome oggetto e DNS in nome alternativo con FQDN del gateway e verificare che nella chiave privata sia selezionata l'opzione Imposta chiave privata esportabile in opzioni chiave. 
    
4. Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.
    
5. I gateway PSTN in un sito PSTN devono connettersi solo ai server di mediazione nello stesso sito.
    
## <a name="set-up-your-users-in-office-365"></a>Configurare gli utenti in Office 365

Accedere al portale di amministrazione di Office 365, aggiungere gli utenti che verranno abilitati per i servizi vocali online e assegnare una licenza E5 o un sistema telefonico nel componente aggiuntivo di Office 365 alla licenza E3 per questi utenti. Per informazioni sull'aggiunta di utenti, vedere [aggiungere utenti a Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Abilitare gli utenti per il sistema telefonico in Office 365 servizi vocali e della segreteria telefonica

Dopo aver aggiunto gli utenti a Office 365, abilitare gli account per il sistema telefonico in Office 365 Voice Services, inclusa la segreteria telefonica. Per abilitare queste funzionalità, è necessario accedere al tenant di Office 365 con un account che è un ruolo di amministratore globale di Office 365 ed essere in grado di eseguire una sessione remota di PowerShell. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Assegnare i criteri all'utente e configurare il numero di telefono vocale aziendale dell'utente, specificato con il valore del parametro **Identity** :
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Un'identità utente può essere specificata usando l'indirizzo SIP dell'utente, il nome dell'entità utente (UPN) o il nome visualizzato dell'utente in Active Directory, ad esempio "Bob Kelly". Il carattere asterisco\*() può essere usato anche con il nome visualizzato come identità dell'utente. Ad esempio, l'identità "\*rossi" restituisce tutti gli utenti che hanno un nome visualizzato che termina con il valore stringa "Smith".
  
Puoi quindi verificare che gli utenti siano stati aggiunti e abilitati usando lo script seguente:
  
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

È necessario decidere se gli utenti devono essere in grado di effettuare chiamate internazionali. Per impostazione predefinita, le chiamate internazionali sono abilitate. Puoi disabilitare o abilitare gli utenti per la chiamata internazionale usando l'interfaccia di amministrazione di Skype for business online.
  
Per disabilitare le chiamate internazionali per ogni utente, eseguire il cmdlet seguente in Skype for Business Online PowerShell:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Per riabilitare le chiamate internazionali per ogni utente dopo la disattivazione, eseguire lo stesso cmdlet, ma modificare il valore di **PolicyName** in *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Assegnare utenti a siti PSTN

Usare PowerShell remoto del tenant per assegnare un sito agli utenti anche se è stato distribuito solo un singolo sito. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Se non viene assegnato un sito PSTN a un utente, la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e il tenant di Office 365 ritornerà a usare il livello di tenant predefinito (peer Destination) in modo che le chiamate possano essere completate. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurare le impostazioni del server di mediazione ibrida online
<a name="BKMK_ConfigureMediationServer"> </a>

Quando una chiamata P2P viene escalated in una conferenza PSTN, Skype for business online Conferencing Server invierà un invito al Cloud Connector Mediation Server. Per assicurarsi che Office 365 possa instradare l'invito correttamente, è necessario configurare un'impostazione nel tenant online per ogni Mediation Server di Cloud Connector come indicato di seguito: 
  
1. Creare un utente nel portale di amministrazione di Office 365. Usare il nome utente desiderato, ad esempio "MediationServer1".
    
    Usa il dominio SIP predefinito di Cloud Connector (il primo dominio SIP nel file ini) come dominio utente.
    
    Tieni presente che l'assegnazione delle licenze è necessaria solo per la propagazione degli utenti nella directory Skype for business online. Assegnare una licenza di Office 365 (ad esempio E5) all'account creato, consentire fino a un'ora per la propagazione delle modifiche, verificare che gli account utente siano stati provisionati correttamente nella directory di Skype for business online eseguendo il cmdlet seguente e quindi rimuovere il licenza da questo account.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Avviare una sessione remota di PowerShell per tenant Azure AD utilizzando le credenziali di amministratore globale o utente e quindi eseguire il cmdlet seguente per impostare il reparto per l'account utente di Azure AD configurato nel passaggio 1 in "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Avviare una sessione remota di PowerShell per Skype for business con le credenziali di amministratore del tenant di Skype for business e quindi eseguire il cmdlet seguente per impostare il nome di dominio completo di Mediation Server e \<Edge\> server su tale account utente, sostituendo DisplayName con quello visualizzato per l'account creato nel passaggio 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Per identità, usare il nome visualizzato dell'account utente di Office 365 creato per questo Mediation Server.
    
    Per *MediationServerFQDN* , usa il nome di dominio completo interno definito per il Mediation Server.
    
    Per *EdgeServerExternalFQDN* , usa il nome FQDN esterno definito per il proxy di accesso a Edge Server. Se sono presenti più siti PSTN per il connettore Cloud, scegliere il nome di dominio completo del proxy di Access Edge Server assegnato al sito in cui si trova il Mediation Server.
    
4. Se sono presenti più server di mediazione Cloud Connector (più siti, HA), ripetere i passaggi precedenti per ognuno di essi.
    

