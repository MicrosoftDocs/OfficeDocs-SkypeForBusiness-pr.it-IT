---
title: SBA routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di distribuzione principali necessarie e le considerazioni relative al routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9e64dc908bafdd63b17e22716e76c4f04df1409
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588600"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Survivable Branch Appliance (SBA) per il routing diretto-anteprima pubblica


> [!NOTE]
> Si tratta di una versione di anteprima pubblica.

Occasionalmente, un sito del cliente che usa il routing diretto per la connessione al sistema telefonico Microsoft può avvertire un'interruzione di Internet.

Supponiamo che il sito del cliente, detto ramo, non possa connettersi temporaneamente al cloud Microsoft tramite il routing diretto. Tuttavia, l'Intranet all'interno del ramo è ancora completamente funzionante e gli utenti possono connettersi al controller di bordo della sessione che fornisce connettività PSTN.

Questo articolo descrive come usare un Survivable Branch Appliance (SBA) per consentire a Microsoft Phone System di continuare a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in caso di interruzione.

## <a name="prerequisites"></a>Prerequisiti

L'SBA è un codice distribuibile fornito da Microsoft ai fornitori SBC che incorporano il codice nel firmware del proprio SBCs. 

Per ottenere il firmware più recente del controller di bordo della sessione con l'appliance Survivable embedded, contattare il fornitore SBC. Inoltre, è necessario quanto segue:

- SBC deve essere configurato per il bypass multimediale per verificare che il client Microsoft Teams nel sito di succursale possa avere flussi multimediali direttamente con SBC. 

- TLS 1.2 deve essere abilitato nel sistema operativo della SBA VM.

## <a name="supported-teams-clients"></a>Client Team supportati

La funzionalità SBA è supportata nei client Microsoft Team seguenti: 

- Windows desktop di Microsoft Teams 

- Desktop di Microsoft teams macOS 

## <a name="how-it-works"></a>Funzionamento

Durante un'interruzione di Internet, il client teams dovrebbe passare automaticamente alla SBA e le chiamate in corso dovrebbero continuare senza interruzioni. Non è necessaria alcuna azione da parte dell'utente. Non appena il client teams rileva che Internet è alto e tutte le chiamate in uscita sono terminate, il client ritornerà alla modalità operativa normale e si collegherà ad altri servizi di teams. L'SBA caricherà i record di dati delle chiamate raccolti nel cloud e la cronologia delle chiamate verrà aggiornata in modo che queste informazioni siano disponibili per la revisione da parte dell'amministratore del tenant. 

Quando il client Microsoft teams è in modalità offline, è disponibile la seguente funzionalità relativa alle chiamate: 

- Effettuare chiamate PSTN tramite SBA/SBC locale con il flusso di elementi multimediali attraverso SBC.

- Ricezione di chiamate PSTN tramite SBA/SBC locale con il flusso di elementi multimediali attraverso SBC. 

- Tenere premuto e riprendere le chiamate PSTN.

## <a name="configuration"></a>Configurazione

Per il funzionamento della funzionalità SBA, il client Teams deve sapere quali SBAs sono disponibili in ogni sito di succursale e quali SBAs sono assegnati agli utenti di tale sito. I passaggi di configurazione sono i seguenti:

1. Creare il SBAs.
2. Creare i criteri di sopravvivenza della filiale teams.
3. Assegnare il criterio agli utenti.
4. Registrare un'applicazione per l'SBA con Azure Active Directory.

Tutta la configurazione viene eseguita usando i cmdlet di PowerShell per Skype for business online. L'interfaccia di amministrazione di teams non supporta ancora la funzionalità Direct routing SBA. 

Per informazioni sulla configurazione di SBC, con collegamenti alla documentazione del fornitore di SBC, vedere Configurazione del controller bordo sessione alla fine di questo articolo.

### <a name="create-the-sbas"></a>Creare il SBAs

Per creare il SBAs, si utilizzerà il cmdlet New-CsTeamsSurvivableBranchAppliance. Questo cmdlet ha i parametri seguenti:

| Parametro| Descrizione |
| :------------|:-------|
| Identity  | Il nome di dominio completo della SBA  |
| Fqdn | Il nome di dominio completo della SBA |
| Sito | TenantNetworkSite in cui si trova l'SBA |
| Descrizione | Testo in formato gratuito |
|||

Ad esempio:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.dk -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Creare i criteri di sopravvivenza della filiale Teams 

Per creare un criterio, usare il cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet contiene i parametri seguenti. Tieni presente che il criterio può contenere uno o più SBAs.

| Parametro| Descrizione |
| :------------|:-------|
| Identity | Identità del criterio |
| BranchApplianceFqdns  | Il nome di dominio completo dello SBA (s) nel sito |
||

Ad esempio:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.dk, sba2.contoso.com} 
```

Puoi aggiungere o rimuovere SBAs da un criterio usando il cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy. Ad esempio: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Assegnare un criterio a un utente

Per assegnare il criterio a singoli utenti, si utilizzerà il cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Questo cmdlet contiene i parametri seguenti:

| Parametro| Descrizione |
| :------------|:-------|
| Identity | Identità dell'utente |
| PolicyName | Identità del criterio |
||

Ad esempio:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

È possibile rimuovere un criterio da un utente concedendo il criterio $Null come illustrato nell'esempio seguente:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrare un'applicazione per l'SBA con Azure Active Directory

Per consentire diversi SBAs usati all'interno del tenant per leggere i dati richiesti da Microsoft 365, è necessario registrare un'applicazione per l'ASB con Azure Active Directory. 

Per altre informazioni sulla registrazione delle applicazioni, vedere quanto segue:

- [Sviluppare app line-of-business per Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registrare un'applicazione con la piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).  

Devi solo registrare una sola applicazione per l'uso da parte di tutti i SBAs nel tenant. 

Per la registrazione SBA sono necessari i valori seguenti creati dalla registrazione: 

- ID applicazione (client) 
- Segreto client 

Per l'applicazione SBA, tieni presente quanto segue: 

- Il nome può essere quello che si decide.  
- Tipi di account supportati = solo account nella directory dell'organizzazione. 
- L'URI di reindirizzamento Web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Token di concessione impliciti = token di accesso e token di ID. 
- Autorizzazioni API = Skype and Teams tenant Access-> autorizzazioni per le applicazioni-> application_access_custom_sba_appliance.
- Segreto client: è possibile usare qualsiasi descrizione e scadenza. 
- Ricordarsi di copiare il segreto client subito dopo averlo creato. 
- L'ID applicazione (client) viene visualizzato nella scheda Panoramica.

Seguire questa procedura:

1. Registrare l'applicazione.
2. Impostare i token di concessione impliciti.
3. Impostare le autorizzazioni API.
4. Creare il segreto client.


## <a name="session-border-controller-configuration"></a>Configurazione del controller del bordo della sessione 

Per informazioni dettagliate su come configurare il controller di bordo della sessione con l'appliance Survivable Branch incorporata, vedere la documentazione fornita dal fornitore SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Ribbon](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Segnalazione dei problemi

Segnalare eventuali problemi all'organizzazione di supporto del fornitore SBC. Quando si segnala il problema, indicare di avere un Survivable Branch Appliance configurato.

## <a name="known-issues"></a>Problemi noti

- Quando si aggiungono nuovi dispositivi Survivable Branch, potrebbe essere necessario un po' di tempo prima di poterli usare in criteri Survivable Branch Appliance.

- Quando si assegna un criterio Survivable Branch Appliance a un utente, potrebbe essere necessario un po' di tempo prima che l'SBA venga visualizzato nell'output di Get-CsOnlineUser. 

- La ricerca in numero inverso rispetto ai contatti di Azure AD non viene eseguita. 

- L'SBA non supporta le impostazioni di inoltro di chiamata. 

- L'esecuzione di una chiamata di emergenza a un numero di emergenza configurato per la chiamata di emergenza dinamica (E911) non è supportata.

- L'output di Get-CsOnlineUser Mostra TeamsBranchSurvivabilityPolicy.
