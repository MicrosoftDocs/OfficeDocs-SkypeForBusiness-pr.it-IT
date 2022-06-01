---
title: Direct Routing SBA
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
description: Altre informazioni sull'instradamento diretto, ad esempio la configurazione, le decisioni di distribuzione di base necessarie e considerazioni sul routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f087498d3a9d679ea10ba2c8cc9505ab772d85ab
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823647"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Survivable Branch Appliance (SBA) per routing diretto


In alcuni casi, un sito del cliente che usa il routing diretto per connettersi a Telefono Microsoft Sistema potrebbe riscontrare un'interruzione di Internet.

Si supponga che il sito del cliente, denominato ramo, non sia temporaneamente in grado di connettersi al cloud Microsoft tramite routing diretto. Tuttavia, la intranet all'interno del ramo è ancora completamente funzionante e gli utenti possono connettersi al session border controller (SBC) che fornisce la connettività PSTN.

In questo articolo viene descritto come utilizzare un Survivable Branch Appliance (SBA) per consentire a Telefono Microsoft System di continuare a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in caso di interruzione del servizio.

## <a name="prerequisites"></a>Prerequisiti

L'SBA è codice distribuibile fornito da Microsoft ai fornitori di SBC che incorporano codice nel firmware o lo distribuiscono separatamente per l'esecuzione di SBA su una macchina virtuale o un hardware separato. 

Per ottenere l'ultimo firmware session border controller con il Survivable Branch Appliance incorporato, contatta il fornitore SBC. Inoltre, è necessario quanto segue:

- SBC deve essere configurato per Media Bypass per garantire che il client Microsoft Teams nel sito di succursale possa avere supporti che fluiscono direttamente con SBC. 

- TLS1.2 deve essere abilitato nel sistema operativo SBA VM.
- Le porte 3443, 4444 e 8443 vengono utilizzate da Microsoft SBA Server per comunicare con il client Teams e devono essere consentite sul firewall. 
- La porta 5061 (o quella configurata in SBC) viene utilizzata da Microsoft SBA Server per comunicare con SBC e deve essere consentita nel firewall. 
- La porta UDP 123 viene utilizzata da Microsoft SBA Server per comunicare con il server NTP e deve essere consentita nel firewall.
- La porta 443 viene utilizzata da Microsoft SBA Server per comunicare con Microsoft 365 e deve essere consentita nel firewall.
- Gli intervalli IP e i tag di servizio di Azure per il cloud pubblico devono essere definiti in base alle linee guida descritte in: https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>Client Teams supportati

La funzionalità SBA è supportata nei client Microsoft Teams seguenti: 

- Microsoft Teams Windows desktop 

- Microsoft Teams macOS desktop
- Teams per dispositivi mobili 
- telefoni Teams

## <a name="how-it-works"></a>Come funziona

Durante un'interruzione di Internet, il client Teams dovrebbe passare automaticamente all'SBA e le chiamate in corso dovrebbero continuare senza interruzioni. Non è richiesta alcuna azione da parte dell'utente. Non appena il client Teams rileva che Internet è attivo e tutte le chiamate in uscita sono finite, il client tornerà alla modalità di funzionamento normale e si connetterà ad altri servizi di Teams. L'SBA caricherà i record dei dati delle chiamate raccolti nel cloud e la cronologia delle chiamate verrà aggiornata in modo che queste informazioni siano disponibili per la revisione da parte dell'amministratore del tenant. 

Quando il client Microsoft Teams è in modalità offline, sono disponibili le seguenti funzionalità correlate alle chiamate: 

- Effettuare chiamate PSTN tramite SBA/SBC locale con elementi multimediali che attraversano la rete SBC.

- Ricezione di chiamate PSTN tramite SBA/SBC locale con elementi multimediali che attraversano il server SBC. 

- Mettere in attesa e riprendere le chiamate PSTN.

## <a name="configuration"></a>Configurazione

Per il funzionamento della funzionalità SBA, il client Teams deve sapere quali AA sono disponibili in ogni sito di succursale e quali CA sono assegnate agli utenti del sito. I passaggi di configurazione sono i seguenti:

1. Creare gli SBA.
2. Creare i criteri di sopravvivenza del ramo Teams.
3. Assegnare il criterio agli utenti.
4. Registra un'applicazione per L'SBA con Azure Active Directory.

Tutta la configurazione viene eseguita usando i cmdlet di PowerShell di Skype for Business Online. L'interfaccia di amministrazione di Teams non supporta ancora la funzionalità SBA routing diretto. 

Per informazioni sulla configurazione di SBC, con collegamenti alla documentazione del fornitore di SBC, vedere Configurazione di Session Border Controller alla fine di questo articolo.

### <a name="create-the-sbas"></a>Creare gli SBA

Per creare gli SBA, si userà il cmdlet New-CsTeamsSurvivableBranchAppliance. Questo cmdlet ha i seguenti parametri:

| Parametro| Descrizione |
| :------------|:-------|
| Identity  | L'identità dell'SBA  |
| Fqdn | Fqdn dell'SBA |
| Sito | SitoRete Tenant in cui si trova l'SBA |
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

### <a name="create-the-teams-branch-survivability-policy"></a>Creare i criteri di sopravvivenza del ramo Teams 

Per creare un criterio, usare il cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet ha i seguenti parametri. Si noti che il criterio può contenere uno o più AAS.

| Parametro| Descrizione |
| :------------|:-------|
| Identity | L'identità del criterio |
| BranchApplianceFqdns  | FQDN degli SBA nel sito |
||

Ad esempio:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

È possibile aggiungere o rimuovere gli assistenti alla posta elettronica da un criterio usando il cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy. Ad esempio: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Assegnare criteri a un utente

Per assegnare il criterio ai singoli utenti, si userà il cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet ha i seguenti parametri:

| Parametro| Descrizione |
| :------------|:-------|
| Identity | Identità dell'utente |
| PolicyName | L'identità del criterio |
||

Ad esempio:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

È possibile rimuovere un criterio da un utente concedendo il criterio $Null come illustrato nell'esempio seguente:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registra un'applicazione per l'SBA con Azure Active Directory

Per consentire ai diversi amministratori di database usati all'interno del tenant di leggere i dati richiesti da Microsoft 365, è necessario registrare un'applicazione per l'SBA con Azure Active Directory. 

Per ulteriori informazioni sulla registrazione della domanda, vedere:

- [Sviluppare app line-of-business per Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registra un'applicazione nel Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app).  

È necessario registrare una sola applicazione per l'uso da parte di tutte le autorità di funzionalità del tenant. 

Per la registrazione SBA, sono necessari i seguenti valori creati dalla registrazione: 

- ID applicazione (client) 
- Segreto client 

Per l'applicazione SBA, tenere presente quanto segue: 

- Il nome può essere qualsiasi cosa tu decida.  
- Tipi di account supportati = Account solo in questa directory organizzativa. 
- Uri di reindirizzamento Web = https://login.microsoftonline.com/common/oauth2/nativeclient.
- Token di concessione implicita = token di accesso e token ID. 
- Autorizzazioni API = Skype e Teams Tenant Amministrazione Access -> Autorizzazioni applicazione -> application_access_custom_sba_appliance.
- Segreto client: puoi usare qualsiasi descrizione e scadenza. 
- Ricordarsi di copiare il segreto client subito dopo averlo creato. 
- L'ID applicazione (client) viene visualizzato nella scheda Panoramica.

Esegui quindi questa procedura:

1. Registra l'applicazione.
2. Impostare i token di concessione implicita.
3. Impostare le autorizzazioni API.
4. Creare il segreto client.


## <a name="session-border-controller-configuration"></a>Configurazione del controller dei confini della sessione 

Per indicazioni dettagliate su come configurare session border controller con Survivable Branch Appliance incorporato, vedere la documentazione fornita dal fornitore di SBC: 

- [AudioCodes](https://www.audiocodes.com/library/technical-documents?query=sba)

- [Ribbon](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Segnalazione di problemi

Segnalare eventuali problemi all'organizzazione di supporto del fornitore di SBC. Quando segnala il problema, indica che hai configurato Survivable Branch Appliance.

## <a name="known-issues"></a>Problemi noti

- Quando si aggiungono nuovi Survivable Branch Appliance, potrebbe essere necessario del tempo prima che sia possibile usarli nei criteri survivable Branch Appliance.

- Quando si assegnano criteri survivable Branch Appliance a un utente, potrebbe essere necessario del tempo prima che l'SBA venga visualizzato nell'output di Get-CsOnlineUser. 

- La ricerca del numero inverso nei contatti di Azure AD non viene eseguita. 

- L'SBA non supporta le impostazioni di inoltro di chiamata. 

- Effettuare una chiamata di emergenza a un numero di emergenza configurato per le chiamate di emergenza dinamiche (E911) non è supportato.
