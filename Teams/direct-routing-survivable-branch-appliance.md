---
title: Routing diretto SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di distribuzione di base necessarie e considerazioni sul routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196490"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Appliance diramazione configurabile (SBA) per il routing diretto


In alcuni casi, un sito del cliente che usa l'instradamento diretto per connettersi al Sistema telefonico Microsoft potrebbe verificarsi un'interruzione di Internet.

Si supponga che il sito del cliente, detto ramo, non sia temporaneamente in grado di connettersi al cloud Microsoft tramite l'instradamento diretto. Tuttavia, la Intranet all'interno del ramo è ancora completamente funzionale e gli utenti possono connettersi al controller dei confini della sessione (SBC) che fornisce connettività PSTN.

In questo articolo viene descritto come utilizzare un appliance SBA (ESA) per consentire al Sistema telefonico Microsoft di continuare a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in caso di interruzione del servizio.

## <a name="prerequisites"></a>Prerequisiti

L'SBA è codice distribuibile fornito da Microsoft ai fornitori di SBC che quindi incorporano il codice nel firmware o lo distribuiscono separatamente per eseguirlo in una macchina virtuale o hardware separata. 

Per ottenere l'ultima versione del firmware session border controller con l'appliance SBC embedded, contattare il fornitore del controller SBC. Inoltre, è necessario quanto segue:

- È necessario configurare SBC per il bypass multimediale per garantire che il client Microsoft Teams nel sito di succursale possa disporre di elementi multimediali direttamente con SBC. 

- TLS1.2 deve essere abilitato nel sistema operativo SBA VM.

## <a name="supported-teams-clients"></a>Client di Teams supportati

La funzionalità SBA è supportata nei client Microsoft Teams seguenti: 

- Microsoft Teams per Windows desktop 

- Microsoft Teams macOS desktop 

## <a name="how-it-works"></a>Come funziona

Durante un'interruzione della connessione Internet, il client Teams dovrebbe passare automaticamente all'SBA e le chiamate in corso dovrebbero continuare senza interruzioni. Non è richiesta alcuna azione da parte dell'utente. Non appena il client Teams rileva che Internet è in funzione e le chiamate in uscita sono completate, il client torna alla modalità normale e si connette ad altri servizi di Teams. L'SBA carica i dati di chiamata raccolti nel cloud e la cronologia delle chiamate viene aggiornata in modo che queste informazioni siano disponibili per la revisione da parte dell'amministratore del tenant. 

Quando il client Microsoft Teams è in modalità offline, è disponibile la seguente funzionalità correlata alle chiamate: 

- Effettuare chiamate PSTN tramite SBA/SBC locale con elementi multimediali che attraversano l'SBC.

- Ricezione di chiamate PSTN tramite SBA/SBC locale con elementi multimediali che attraversano l'SBC. 

- In attesa e ripresa delle chiamate PSTN.

## <a name="configuration"></a>Configurazione

Per il funzionamento della funzionalità SBA, il client Teams deve sapere quali SBA sono disponibili in ogni sito di succursale e quali SBA sono assegnate agli utenti nel sito. I passaggi di configurazione sono i seguenti:

1. Creare gli SBA.
2. Creare i criteri di affidabilità dei rami di Teams.
3. Assegnare il criterio agli utenti.
4. Registrare un'applicazione per sBA con Azure Active Directory.

Tutte le configurazioni vengono eseguite usando i cmdlet di PowerShell di Skype for Business Online. L'interfaccia di amministrazione di Teams non supporta ancora la funzionalità Direct Routing SBA. 

Per informazioni sulla configurazione di SBC, con collegamenti alla documentazione del fornitore di SBC, vedere la configurazione di Session Border Controller alla fine di questo articolo.

### <a name="create-the-sbas"></a>Creare gli SBA

Per creare gli SBA, si userà il cmdlet New-CsTeamsSurvivableBranchAppliance istruzione. Questo cmdlet contiene i parametri seguenti:

| Parametro| Descrizione |
| :------------|:-------|
| Identity  | Identità dell'SBA  |
| Fqdn | Nome di dominio completo dell'SBA |
| Sito | TenantNetworkSite in cui si trova l'SBA |
| Descrizione | Testo in formato libero |
|||

Ad esempio:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Creare i criteri di affidabilità dei rami di Teams 

Per creare un criterio, usare il cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet contiene i parametri seguenti. Si noti che il criterio può contenere uno o più SBA.

| Parametro| Descrizione |
| :------------|:-------|
| Identity | Identità del criterio |
| BranchApplianceFqdns  | Nome completo degli SBA nel sito |
||

Ad esempio:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

È possibile aggiungere o rimuovere gli SBA da un criterio usando il cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy locale. Ad esempio: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Assegnare criteri a un utente

Per assegnare il criterio a singoli utenti, si userà il cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet contiene i parametri seguenti:

| Parametro| Descrizione |
| :------------|:-------|
| Identity | Identità dell'utente |
| PolicyName | Identità dei criteri |
||

Ad esempio:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

È possibile rimuovere un criterio da un utente concedendo il criterio di $Null predefinito, come illustrato nell'esempio seguente:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrare un'applicazione per sBA con Azure Active Directory

Per consentire a SBA diversi usati all'interno del tenant di leggere i dati necessari da Microsoft 365, è necessario registrare un'applicazione per l'SBA in Azure Active Directory. 

Per altre informazioni sulla registrazione delle applicazioni, vedere:

- [Sviluppare app line-of-business per Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrare un'applicazione nella piattaforma di identità Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)  

È necessario registrare una sola applicazione per l'uso da parte di tutti gli account di servizio (SBA) nel tenant. 

Per la registrazione dell'SBA, sono necessari i valori seguenti creati dalla registrazione: 

- ID applicazione (client) 
- Segreto client 

Per l'applicazione SBA, tenere presente quanto segue: 

- Il nome può essere quello che si decide.  
- Tipi di account supportati = Account solo in questa directory organizzativa. 
- L'URI reindirizzamento Web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Token di concessione impliciti = token di accesso e token ID. 
- Autorizzazioni API = Accesso amministratore tenant Skype e Teams -> autorizzazioni applicazione -> application_access_custom_sba_appliance.
- Segreto client: è possibile usare qualsiasi descrizione e scadenza. 
- Ricordarsi di copiare il segreto client immediatamente dopo la creazione. 
- ID applicazione (client) visualizzato nella scheda Panoramica.

Quindi, seguire questa procedura:

1. Registrare l'applicazione.
2. Impostare i token di concessione impliciti.
3. Impostare le autorizzazioni API.
4. Creare il segreto client.


## <a name="session-border-controller-configuration"></a>Configurazione di Session Border Controller 

Per istruzioni dettagliate su come configurare il controller dei confini della sessione con l'appliance Diramazione configurabile incorporato, vedere la documentazione fornita dal fornitore di SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Barra multifunzione](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Segnalazione di problemi

Segnalare eventuali problemi all'organizzazione di supporto del fornitore di SBC. Quando si segnala il problema, indicare che è stato configurato un appliance diramazione configurabile.

## <a name="known-issues"></a>Problemi noti

- Quando si aggiungono nuovi appliance per branch utilizzabili, può essere necessario del tempo prima che sia possibile usarli nei criteri per le appliance di succursale configurabili.

- Quando si assegnano i criteri per l'appliance a ramo configurabile a un utente, può essere necessario del tempo prima che l'SBA venga visualizzato nell'output di Get-CsOnlineUser. 

- La ricerca inversa dei numeri nei contatti di Azure AD non viene eseguita. 

- L'SBA non supporta le impostazioni di inoltro di chiamata. 

- Non è possibile effettuare chiamate di emergenza a un numero di emergenza configurato per le chiamate di emergenza dinamiche (E911).

- L'output Get-CsOnlineUser mostra TeamsBranchSurvivabilityPolicy.
