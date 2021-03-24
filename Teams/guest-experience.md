---
title: Esperienza Guest in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Questo articolo descrive la funzionalità Microsoft Teams disponibile per gli utenti guest.
ms.openlocfilehash: 8eda5d3cabf497d105c0fd4a4610ba59db128bfc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092084"
---
# <a name="guest-experience-in-teams"></a>Esperienza guest in Teams

Quando un utente guest è invitato a unirsi a un team, riceve un messaggio di posta elettronica di benvenuto. Questo messaggio include alcune informazioni sul team e su cosa aspettarsi ora che si è membri. L'utente guest deve accettare l'invito selezionando **Apri Microsoft Teams** nel messaggio di posta elettronica prima di poter accedere al team e ai relativi canali.
    
![Screenshot che mostra un esempio di un messaggio di posta elettronica di benvenuto](media/guest-experience-image1.png)
    
Tutti i membri del team visualizzano un messaggio nel thread del canale che annuncia che il proprietario del team ha aggiunto un utente guest e fornisce il nome di tale utente. Tutti i membri del team possono identificare facilmente chi è un utente guest. Un tag nell'angolo in alto a destra del thread del canale indica il numero di utenti guest nel team e un'etichetta **(Guest)** viene visualizzata accanto al nome di ogni utente guest.

![Screenshot che mostra il tag che indica il numero di utenti guest nel team](media/guest-experience-image2.png)

Guardare questi video sull'esperienza guest in Teams:
- [Partecipare a un team come Guest](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Partecipare a una riunione di Teams con guest](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Confronto tra le funzionalità dei membri del team e degli utenti guest

La tabella seguente consente di confrontare le funzionalità di Teams disponibili per i membri del team di un'organizzazione e per gli utenti guest. Gli amministratori di Teams controllano le funzionalità disponibili per gli utenti guest.

| Funzionalità in Teams | Utenti di Teams nell'organizzazione | Guest |
|:-----|:-----|:-----|
|Creare un canale  <br/>  *I proprietari del team controllano questa impostazione.*  <br/> |&#x2713;|&#x2713;|
|Partecipare a una chat privata  <br/> |&#x2713;|&#x2713;|
|Partecipare a una conversazione sul canale  <br/> |&#x2713;|&#x2713;|
|Pubblicare, eliminare e modificare messaggi  <br/> |&#x2713;|&#x2713;|
|Condividere un file di canale  <br/> |&#x2713;|&#x2713;|
|Accedere ai file di SharePoint<br/> |&#x2713;|&#x2713;|
|Allegare file<br/> |&#x2713;|Solo chat del team|
|Scaricare file di chat private<br/> |&#x2713;|&#x2713;|
|Eseguire ricerche all'interno di file<br/> |&#x2713;||
|Condividere un file di chat  <br/> |&#x2713;||
|Aggiungere app (schede, bot o connettori)  <br/> |&#x2713;||
|Creare riunioni o accedere a pianificazioni  <br/> |&#x2713;||
|Accedere allo spazio di archiviazione di OneDrive for Business  <br/> |&#x2713;||
|Creare criteri di accesso guest a livello di tenant e a team/canali  <br/> |&#x2713;||
|Invitare un utente esterno al dominio dell'organizzazione di Microsoft 365 o Office 365 <br/>  *I proprietari del team controllano questa impostazione.*  <br/> <br/> |&#x2713;||
|Creare un team  <br/> |&#x2713;||
|Individuare e partecipare a un team pubblico  <br/> |&#x2713;||
|Visualizzare un organigramma  <br/> |&#x2713;||
|Usare la traduzione incorporata  <br/> |&#x2713;||
|Diventare un proprietario del team  <br/> |&#x2713;||

La tabella seguente mostra le funzionalità per chiamate e riunioni disponibili per gli utenti guest rispetto ad altri tipi di utenti.

| Funzionalità per le chiamate | Guest | Utenti E1 ed E3 | Utente E5 e con VoIP aziendale |
| --------------- | ----- | -------------- | -------------- |
| Chiamate VoIP | Sì | Sì | Sì |
| Chiamate di gruppo | Sì | Sì | Sì |
| Controlli chiamata principali supportati (messa in attesa, disattivazione audio, attivazione/disattivazione video, condivisione dello schermo) | Sì | Sì | Sì |
| Destinazione di trasferimento | Sì | Sì | Sì |
| Possibilità di trasferire una chiamata | Sì | Sì | Sì |
| Possibilità di trasferimento di consulenza | Sì | Sì | Sì |
| Possibilità di aggiungere altri utenti a una chiamata tramite VOIP | Sì | Sì | Sì |
| Possibilità di aggiungere utenti in base al numero di telefono a una chiamata | No | No | Sì |
| Inoltro di chiamata | No | Sì | Sì |
| Destinazione gruppo autorizzato alla risposta | No | Sì | Sì |
| Destinazione senza risposta | No | Sì | Sì |
| Possibilità di essere la destinazione di una chiamata federata | No | Sì | Sì |
| Possibilità di effettuare una chiamata federata | No | Sì | Sì |
| Possibilità di inoltrare immediatamente le proprie chiamate | No | No | Sì |
| Possibilità di far squillare contemporaneamente le proprie chiamate | No | No | Sì |
| Possibilità di instradare le proprie chiamate senza risposta | No | No | Sì |
| Le chiamate perse possono passare alla segreteria telefonica | No | No<sup>1</sup> |Sì |
| Avere un numero di telefono che può ricevere chiamate | No | No | Sì |
| Possibilità di comporre numeri di telefono | No | No | Sì |
| Possibilità di accedere alle impostazioni delle chiamate | No | No | Sì |
| Possibilità di modificare il messaggio di saluto della segreteria telefonica | No | No<sup>1</sup> | Sì |
| Possibilità di cambiare le suonerie | No | No  | Sì |
| Supporta TTY | No | No | Sì |
| Possibilità di avere delegati | No | No | Sì |
|  Possibilità di essere un delegato | No | No | Sì |

<sup>1</sup> Questa funzionalità sarà disponibile tra breve.

> [!NOTE]
> Il criterio **Restrizioni di accesso degli utenti guest** in Azure Active Directory (Azure AD) determina le autorizzazioni per gli utenti guest nella directory. Esistono tre opzioni per i criteri.
>  - Gli **utenti guest hanno lo stesso accesso dei membri (più inclusivo)** impostazioni significa che i guest hanno lo stesso accesso ai dati della directory degli utenti regolari nel tuo elenco.
>  - Gli **utenti guest hanno accesso limitato alle proprietà e all'appartenenza agli oggetti directory** impostazioni significa che gli utenti guest non hanno le autorizzazioni per determinate attività della directory, ad esempio per l'enumerazione di utenti, gruppi o altre risorse della directory con Microsoft Graph.
>  - L' **accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti della directory (più restrittivo),** impostazioni significa che gli utenti guest possono accedere solo agli oggetti della directory.
>
>Per altre informazioni, vedere [Cosa sono le autorizzazioni utente predefinite in Azure Active Directory?](/azure/active-directory/fundamentals/users-default-permissions)

## <a name="related-topics"></a>Argomenti correlati

[Abbandonare un organizzazione come utente guest](/azure/active-directory/b2b/leave-the-organization)