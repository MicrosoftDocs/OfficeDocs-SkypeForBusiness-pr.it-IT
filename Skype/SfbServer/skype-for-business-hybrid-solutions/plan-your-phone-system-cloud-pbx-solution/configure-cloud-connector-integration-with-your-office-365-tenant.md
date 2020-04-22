---
title: Configurare l'integrazione del connettore Cloud con l'organizzazione Microsoft 365 o Office 365
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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Informazioni su come configurare l'integrazione del connettore Cloud con l'organizzazione di Office 365.
ms.openlocfilehash: 1fecf017f614fc8bdf0f38b5f51c29e4b2774357
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780645"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configurare l'integrazione del connettore Cloud con l'organizzazione Microsoft 365 o Office 365
 
Informazioni su come configurare l'integrazione del connettore Cloud con l'organizzazione di Office 365.
  
Dopo aver completato l'installazione di Skype for Business Cloud Connector Edition, eseguire la procedura descritta in questa sezione per configurare la distribuzione e connetterla all'organizzazione di Office 365.
  
## <a name="configure-firewall-settings"></a>Configurare le impostazioni del firewall

Configurare le impostazioni del firewall per le impostazioni del firewall interno ed esterno per la rete perimetrale per aprire le porte necessarie come descritto in [porte e protocolli](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurare i gateway PSTN (Public Switched Telephone Network)

Configurare trunk su ogni gateway PSTN in modo che punti a Mediation Server per tutti gli elettrodomestici. Poiché il nome FQDN del pool è lo stesso per tutti i server del pool, ciascun trunk deve puntare a un FQDN Mediation Server o a un indirizzo IP anziché all'FQDN del pool di Mediation Server. I trunk devono essere impostati con la stessa priorità.
  
Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e Mediation Server per supportare MTLS, come indicato di seguito:
  
1. Esportare la CA radice dal computer di Active Directory del connettore Cloud.
    
2. Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.
    
3. Importare il certificato della CA radice per il certificato emesso sul gateway nei Mediation Server. Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio autorità di certificazione in esecuzione nel computer del connettore Cloud Active Directory come indicato di seguito:
    
   - Modificare il modello di server Web esistente per consentire agli utenti autenticati di registrare o creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione. Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Richiedere un certificato mediante lo snap-in certificato selezionando il modello di server Web abilitato. Assicurarsi di aggiungere il nome comune in Subject and DNS Name in nome alternativo con il nome di dominio completo del gateway e confermare che la chiave privata che rende esportabile la chiave privata sia selezionata in opzioni chiave. 
    
4. Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.
    
## <a name="update-the-domain-for-your-tenant"></a>Aggiornare il dominio per il tenant

Assicurarsi di aver completato la procedura per aggiornare il dominio in Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Office 365, vedere [aggiungere un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Aggiungere record DNS in Office 365 per il server perimetrale

Aggiungere i seguenti record DNS all'organizzazione di Office 365. Per informazioni su come aggiungere record DNS all'organizzazione di Office 365, vedere [aggiungere o modificare record DNS personalizzati in office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Aggiungere un record A DNS per Access Edge.
    
2. I record SRV verranno creati automaticamente da Office 365 e dagli script di distribuzione. Verificare che sia possibile cercare i due servizi SIP seguenti sul server perimetrale: _sip e _sipfederationtls.
    
     ![Conferma dei record SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configurare la connettività ibrida tra Cloud Connector Edition e Office 365

Per configurare la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e l'organizzazione di Office 365, eseguire il cmdlet seguente in una sessione di PowerShell remota. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
Il cmdlet imposta il nome di dominio completo esterno di Access Edge. Nel primo dei comandi, l' \<FQDN\> del perimetro di accesso esterno deve essere quello per il ruolo Access Edge SIP. Per impostazione predefinita, questo dovrebbe essere il\<nome\>di AP. Domain.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> L'FQDN del perimetro di accesso esterno utilizzato per la destinazione peer deve essere impostato su un sito PSTN che verrà utilizzato solo come fallback nel caso in cui un utente non sia assegnato a un sito PSTN. Per ulteriori informazioni, vedere [deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurare i gateway PSTN

Configurare trunk su ogni gateway PSTN in modo che punti a Mediation Server per tutti gli elettrodomestici. Ogni trunk deve puntare a un FQDN Mediation Server o a un indirizzo IP anziché all'FQDN del pool di Mediation Server, in quanto l'FQDN del pool è lo stesso per tutti i server del pool. I trunk devono essere impostati con la stessa priorità.
  
Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e Mediation Server per supportare MTLS, come indicato di seguito:
  
1. Esportare la CA radice dal computer di Active Directory del connettore Cloud.
    
2. Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.
    
3. Importare il certificato della CA radice per il certificato emesso sul gateway nei Mediation Server. Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio autorità di certificazione in esecuzione nel computer del connettore Cloud Active Directory come indicato di seguito:
    
   - Modificare il modello di server Web esistente per consentire agli utenti autenticati di registrare o creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione. Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Richiedere un certificato mediante lo snap-in certificato selezionando il modello di server Web abilitato. Assicurarsi di aggiungere il nome comune in Subject and DNS Name in nome alternativo con il nome di dominio completo del gateway e confermare che la chiave privata che rende esportabile la chiave privata sia selezionata in opzioni chiave. 
    
4. Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.
    
5. I gateway PSTN in un sito PSTN devono connettersi solo ai Mediation Server nello stesso sito.
    
## <a name="set-up-your-users-in-office-365"></a>Configurare gli utenti in Office 365

Accedere all'interfaccia di amministrazione di Microsoft 365, aggiungere gli utenti che verranno abilitati per i servizi vocali online e assegnare una licenza E5 o un sistema telefonico nel componente aggiuntivo di Office 365 alla licenza E3 per questi utenti. Per informazioni sull'aggiunta di utenti, vedere [aggiungere utenti a Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Abilitare gli utenti per il sistema telefonico nei servizi vocali e vocali di Office 365

Dopo aver aggiunto gli utenti a Office 365, abilitare gli account per il sistema telefonico in Office 365 Voice Services, inclusa la segreteria telefonica. Per abilitare queste funzionalità, è necessario accedere all'organizzazione di Office 365 con un account che sia un ruolo di amministratore globale ed essere in grado di eseguire Remote PowerShell. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- Assegnare il criterio all'utente e configurare il numero di telefono della segreteria telefonica dell'utente, specificato con il valore del parametro **Identity** :
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > È possibile specificare un'identità utente utilizzando l'indirizzo SIP dell'utente, il nome dell'entità utente (UPN) o il nome visualizzato di Active Directory dell'utente (ad esempio, "Bob Kelly"). Il carattere asterisco\*() può essere utilizzato anche con il nome visualizzato come identità dell'utente. Ad esempio, il parametro Identity\*"Smith" restituisce tutti gli utenti che dispongono di un nome visualizzato che termina con il valore stringa "Smith".
  
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

È necessario decidere se gli utenti devono essere in grado di effettuare chiamate internazionali. Per impostazione predefinita, la chiamata internazionale è abilitata. È possibile disabilitare o abilitare gli utenti per la composizione internazionale utilizzando l'interfaccia di amministrazione di Skype for business online.
  
Per disabilitare le chiamate internazionali per ogni utente, eseguire il seguente cmdlet in PowerShell per Skype for business online:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Per riabilitare la chiamata internazionale per ogni utente dopo che è stata disattivata, eseguire lo stesso cmdlet, ma cambiare il valore di **PolicyName** in *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Assegnare gli utenti ai siti PSTN

Utilizzare PowerShell remote tenant per assegnare un sito agli utenti anche se è stato distribuito un singolo sito. Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Se a un utente non è assegnato alcun sito PSTN, la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e l'organizzazione di Office 365 ritornerà a utilizzare il livello tenant default One (peer Destination) in modo che le chiamate possano essere completate. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurare le impostazioni di Mediation server ibrido online
<a name="BKMK_ConfigureMediationServer"> </a>

Quando una chiamata P2P viene inoltrata a una conferenza PSTN, Skype for business online Conferencing Server invierà un invito a Cloud Connector Mediation Server. Per assicurarsi che Office 365 sia in grado di instradare correttamente l'invito, è necessario configurare un'impostazione nel tenant online per ogni Mediation Server Cloud Connector come indicato di seguito: 
  
1. Creare un utente nell'interfaccia di amministrazione di Microsoft 365. Utilizzare qualsiasi nome utente desiderato, ad esempio "MediationServer1".
    
    Utilizzare il dominio SIP predefinito del connettore Cloud (il primo dominio SIP nel file. ini) come dominio utente.
    
    Tenere presente che l'assegnazione della licenza è necessaria solo per la propagazione degli utenti nella directory di Skype for business online. Assegnare una licenza di Office 365 (ad esempio E5) all'account creato, consentire fino a un'ora per la propagazione delle modifiche, verificare che gli account utente siano stati provisionati correttamente nella directory di Skype for business online eseguendo il cmdlet seguente e quindi rimuovere la licenza da questo account.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Avviare una sessione Tenant Azure AD Remote PowerShell utilizzando le credenziali di amministratore globale o utente, quindi eseguire il seguente cmdlet per impostare il reparto per l'account utente di Azure AD configurato nel passaggio 1 su "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Avviare una sessione di PowerShell remota di Skype for business con le credenziali di amministratore del tenant di Skype for business, quindi eseguire il seguente cmdlet per impostare l'FQDN di Mediation Server e server perimetrale \<su\> tale account utente, sostituendo DisplayName con il nome visualizzato dell'utente per l'account creato nel passaggio 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Per Identity, utilizzare il nome visualizzato dell'account utente creato per questo Mediation Server.
    
    Per *MediationServerFQDN* , utilizzare il nome di dominio completo interno definito per il Mediation Server.
    
    Per *EdgeServerExternalFQDN* , utilizzare il nome di dominio completo esterno definito per il proxy di accesso Edge Server. Se sono presenti più siti PSTN del connettore Cloud, scegliere il nome di dominio completo del proxy di accesso server perimetrale assegnato al sito in cui si trova il Mediation Server.
    
4. Se sono presenti più Mediation Server del connettore Cloud (più siti, HA), ripetere i passaggi precedenti per ognuno di essi.
    

