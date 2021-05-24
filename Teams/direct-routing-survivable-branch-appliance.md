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
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di base necessarie per la distribuzione e le considerazioni sul routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589240"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>SBA (Survivable Branch Appliance) per il routing diretto


In alcuni casi, un sito del cliente che usa Routing diretto per connettersi Telefono Microsoft sistema potrebbe verificarsi un'interruzione di Internet.

Si supponga che il sito del cliente, denominato filiale, temporaneamente non possa connettersi al cloud Microsoft tramite Routing diretto. Tuttavia, la Intranet all'interno del ramo è ancora completamente funzionante e gli utenti possono connettersi al Session Border Controller (SBC) che fornisce la connettività PSTN.

Questo articolo descrive come usare un Survivable Branch Appliance (SBA) per consentire a Telefono Microsoft System di continuare a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in caso di interruzione.

## <a name="prerequisites"></a>Prerequisiti

L'SBA è un codice distribuibile fornito da Microsoft ai fornitori SBC che incorporano il codice nel firmware o lo distribuiscono separatamente per fare in modo che SBA sia eseguito in una macchina virtuale o hardware separata. 

Per ottenere il firmware più recente di Session Border Controller con il Survivable Branch Appliance incorporato, contattare il fornitore SBC. Inoltre, è necessario quanto segue:

- L'SBC deve essere configurato per Media Bypass per assicurarsi che il client Microsoft Teams nel sito di succursale possa avere elementi multimediali che fluino direttamente con SBC. 

- TLS1.2 deve essere abilitato nel sistema operativo della macchina virtuale SBA.

## <a name="supported-teams-clients"></a>Client Teams supportati

La caratteristica SBA è supportata nei client Microsoft Teams seguenti: 

- Microsoft Teams Windows desktop 

- Microsoft Teams desktop macOS 

## <a name="how-it-works"></a>Come funziona

Durante un'interruzione di Internet, il client Teams passare automaticamente all'SBA e le chiamate in corso dovrebbero continuare senza interruzioni. Non è richiesta alcuna azione da parte dell'utente. Non appena il client Teams rileva che Internet è in funzione e le chiamate in uscita vengono completate, il client torna alla normale modalità di funzionamento e si connette ad altri Teams servizi. L'SBA carica i record dei dati delle chiamate raccolti nel cloud e la cronologia delle chiamate viene aggiornata in modo che queste informazioni siano disponibili per la revisione da parte dell'amministratore del tenant. 

Quando il client Microsoft Teams è in modalità offline, è disponibile la funzionalità correlata alle chiamate seguente: 

- Effettuare chiamate PSTN tramite SBA/SBC locale con elementi multimediali che fluire attraverso la SBC.

- Ricezione di chiamate PSTN tramite SBA/SBC locale con elementi multimediali che scorrono attraverso la SBC. 

- Blocco e ripresa delle chiamate PSTN.

## <a name="configuration"></a>Configurazione

Per il funzionamento della caratteristica SBA, il client di Teams deve sapere quali SBA sono disponibili in ogni sito di succursale e quali SBA sono assegnate agli utenti del sito. I passaggi di configurazione sono i seguenti:

1. Creare le SBA.
2. Creare i criteri di Teams di succursale.
3. Assegnare il criterio agli utenti.
4. Registrare un'applicazione per l'SBA con Azure Active Directory.

Tutta la configurazione viene eseguita usando Skype for Business cmdlet di PowerShell online. L'Teams di amministrazione non supporta ancora la funzionalità SBA Routing diretto. 

Per informazioni sulla configurazione di SBC, con collegamenti alla documentazione del fornitore SBC, vedere Configurazione di Session Border Controller alla fine di questo articolo.

### <a name="create-the-sbas"></a>Creare le SBA

Per creare le SBA, si userà il cmdlet New-CsTeamsSurvivableBranchAppliance. Questo cmdlet ha i parametri seguenti:

| Parametro| Descrizione |
| :------------|:-------|
| Identity  | Identità dell'SBA  |
| Fqdn | FQDN dell'SBA |
| Sito | TenantNetworkSite in cui si trova l'SBA |
| Descrizione | Formato testo libero |
|||

Ad esempio:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Creare i criteri Teams di succursale 

Per creare un criterio, usare il cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet ha i parametri seguenti. Si noti che il criterio può contenere uno o più SBA.

| Parametro| Descrizione |
| :------------|:-------|
| Identity | Identità dei criteri |
| BranchApplianceFqdns  | FQDN degli SBA nel sito |
||

Ad esempio:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

È possibile aggiungere o rimuovere IAS da un criterio usando il cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy. Ad esempio: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Assegnare un criterio a un utente

Per assegnare il criterio a singoli utenti, si userà il cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet ha i parametri seguenti:

| Parametro| Descrizione |
| :------------|:-------|
| Identity | L'identità dell'utente |
| PolicyName | Identità dei criteri |
||

Ad esempio:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

È possibile rimuovere un criterio da un utente concedendo $Null criteri di protezione, come illustrato nell'esempio seguente:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrare un'applicazione per l'SBA con Azure Active Directory

Per consentire a SBA diversi usati all'interno del tenant di leggere i dati necessari da Microsoft 365, è necessario registrare un'applicazione per l'SBA con Azure Active Directory. 

Per altre informazioni sulla registrazione dell'applicazione, vedere quanto segue:

- [Sviluppare app line-of-business per Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrare un'applicazione con il Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app).  

È necessario registrare una sola applicazione per l'uso da parte di tutti gli SBA nel tenant. 

Per la registrazione SBA, sono necessari i valori seguenti creati dalla registrazione: 

- ID applicazione (client) 
- Segreto client 

Per l'applicazione SBA, tenere presente quanto segue: 

- Il nome può essere quello che si decide.  
- Tipi di account supportati = Account solo in questa directory dell'organizzazione. 
- Uri di reindirizzamento Web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Token di concessione implicita = token di accesso e token ID. 
- Autorizzazioni API = Skype e Teams di amministrazione tenant -> autorizzazioni dell'applicazione -> application_access_custom_sba_appliance.
- Segreto client: è possibile usare qualsiasi descrizione e scadenza. 
- Ricordarsi di copiare il segreto client subito dopo la creazione. 
- L'ID applicazione (client) viene visualizzato nella scheda Panoramica.

Quindi, seguire questa procedura:

1. Registrare l'applicazione.
2. Impostare i token di concessione impliciti.
3. Impostare le autorizzazioni API.
4. Creare il segreto client.


## <a name="session-border-controller-configuration"></a>Configurazione di Session Border Controller 

Per istruzioni dettagliate su come configurare session border controller con il Survivable Branch Appliance incorporato, vedere la documentazione fornita dal fornitore SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Barra multifunzione](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Segnalazione di problemi

Segnalare eventuali problemi all'organizzazione di supporto del fornitore SBC. Quando si segnala il problema, indicare che è configurato un Survivable Branch Appliance.

## <a name="known-issues"></a>Problemi noti

- Quando si aggiungono nuovi Survivable Branch Appliance, può essere necessario del tempo prima di poterli usare nei criteri di Survivable Branch Appliance.

- Quando si assegnano criteri di Survivable Branch Appliance a un utente, potrebbe essere necessario del tempo prima che l'SBA venga visualizzato nell'output di Get-CsOnlineUser. 

- La ricerca inversa dei numeri nei contatti di Azure AD non viene eseguita. 

- L'SBA non supporta le impostazioni di inoltro di chiamata. 

- L'esecuzione di una chiamata di emergenza a un numero di emergenza configurato per le chiamate di emergenza dinamiche (E911) non è supportata.
