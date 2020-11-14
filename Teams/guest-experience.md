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
description: Questo articolo descrive la funzionalità Microsoft teams disponibile per gli utenti guest.
ms.openlocfilehash: a2c4bcf380eb90f7c0a00c8f6f4f9141b80f8460
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030292"
---
# <a name="guest-experience-in-teams"></a>Esperienza Guest in teams

Quando un ospite è invitato a partecipare a un team, riceve un messaggio di posta elettronica di benvenuto. Questo messaggio include alcune informazioni sul team e cosa aspettarsi ora che siano membri. Il guest deve accettare l'invito selezionando **Apri Microsoft teams** nel messaggio di posta elettronica prima di poter accedere al team e ai relativi canali.
    
![Screenshot che mostra un esempio di messaggio di posta elettronica di benvenuto](media/guest-experience-image1.png)
    
Tutti i membri del team vedono un messaggio nel thread del canale che annuncia che il proprietario del team ha aggiunto un Guest e fornisce il nome dell'ospite. Tutti gli utenti del team possono identificare facilmente chi è ospite. Un tag nell'angolo in alto a destra del thread del canale indica il numero di Guest nel team e viene visualizzata un'etichetta **(Guest)** accanto al nome di ogni Guest.

![Schermata che mostra il contrassegno che indica il numero di Guest nel team](media/guest-experience-image2.png)

Vedere questi video sull'esperienza Guest in teams:
- [Partecipare a un team come Guest](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Partecipare a una riunione di teams con gli ospiti](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Confronto tra i membri del team e le funzionalità Guest

Nella tabella seguente vengono confrontate le funzionalità teams disponibili per i membri del team di un'organizzazione e i relativi Guest. Gli amministratori di teams controllano le funzionalità disponibili per gli utenti.

|**Funzionalità in teams**|**Utenti teams nell'organizzazione**|**Utente Guest**|
|:-----|:-----|:-----|
|Creare un canale  <br/>  *I proprietari del team controllano questa impostazione.*  <br/> |&#x2713;|&#x2713;|
|Partecipare a una chat privata  <br/> |&#x2713;|&#x2713;|
|Partecipare a una conversazione di canale  <br/> |&#x2713;|&#x2713;|
|Pubblicare, eliminare e modificare i messaggi  <br/> |&#x2713;|&#x2713;|
|Condividere un file di canale  <br/> |&#x2713;|&#x2713;|
|Accedere ai file di SharePoint<br/> |&#x2713;|&#x2713;|
|Allegare file<br/> |&#x2713;|&#x2713;|
|Scaricare i file di chat privata<br/> |&#x2713;|&#x2713;|
|Eseguire ricerche nei file<br/> |&#x2713;||
|Condividere un file di chat  <br/> |&#x2713;||
|Aggiungere app (schede, bot o connettori)  <br/> |&#x2713;||
|Creare riunioni o pianificare le sessioni di Access  <br/> |&#x2713;||
|Accedere a OneDrive for Business Storage  <br/> |&#x2713;||
|Creare criteri di accesso Guest a livello di tenant e teams/Channels  <br/> |&#x2713;||
|Invitare un utente esterno al dominio dell'organizzazione Microsoft 365 o Office 365 <br/>  *I proprietari del team controllano questa impostazione.*  <br/> <br/> |&#x2713;||
|Creare un team  <br/> |&#x2713;||
|Individuare e partecipare a un team pubblico  <br/> |&#x2713;||
|Visualizzazione organigramma  <br/> |&#x2713;||
|Usare la traduzione in linea  <br/> |&#x2713;||
|Diventare proprietario del team  <br/> |&#x2713;||

La tabella seguente mostra le funzionalità di chiamata e riunione disponibili per gli ospiti, rispetto ad altri tipi di utenti.

| Caratteristica chiamante | I | Utenti E1 e E3 | E5 e Enterprise Voice User |
| --------------- | ----- | -------------- | -------------- |
| Chiamate VOIP | Sì | Sì | Sì |
| Chiamata di gruppo | Sì | Sì | Sì |
| Controlli di chiamata principali supportati (blocco, mute, video attivato/disattivato, condivisione dello schermo) | Sì | Sì | Sì |
| Destinazione di trasferimento | Sì | Sì | Sì |
| Può trasferire una chiamata | Sì | Sì | Sì |
| Trasferimento consultivo can | Sì | Sì | Sì |
| Può aggiungere altri utenti a una chiamata tramite VOIP | Sì | Sì | Sì |
| Può aggiungere utenti per numero di telefono a una chiamata | No | No | Sì |
| Inoltra destinazione | No | Sì | Sì |
| Destinazione gruppo chiamate | No | Sì | Sì |
| Destinazione senza risposta | No | Sì | Sì |
| Può essere la destinazione di una chiamata federata | No | Sì | Sì |
| Può eseguire una chiamata federata | No | Sì | Sì |
| Può inoltrare immediatamente le chiamate | No | No | Sì |
| Può chiamare simultaneamente le chiamate | No | No | Sì |
| Può instradare le chiamate senza risposta | No | No | Sì |
| Le chiamate perse possono andare alla segreteria telefonica | No | N.<sup>1</sup> |Sì |
| Avere un numero di telefono in grado di ricevere chiamate | No | No | Sì |
| Può chiamare i numeri di telefono | No | No | Sì |
| Può accedere alle impostazioni delle chiamate | No | No | Sì |
| Può cambiare il messaggio di saluto della segreteria | No | N.<sup>1</sup> | Sì |
| Può modificare le suonerie | No | No  | Sì |
| Supporta TTY | No | No | Sì |
| Può avere delegati | No | No | Sì |
|  Può essere un delegato | No | No | Sì |

<sup>1</sup> questa funzionalità sarà presto disponibile.

> [!NOTE]
> Il criterio **restrizioni di accesso utente Guest** in Azure Active Directory (Azure ad) determina le autorizzazioni per gli utenti nella directory. Esistono tre opzioni per i criteri.
>  - Gli **utenti guest hanno lo stesso accesso dei membri (più inclusivo)** impostazioni significa che i guest hanno lo stesso accesso ai dati della directory degli utenti regolari nel tuo elenco.
>  - Gli **utenti guest hanno accesso limitato alle proprietà e all'appartenenza agli oggetti directory** impostazioni significa che gli utenti guest non hanno le autorizzazioni per determinate attività della directory, ad esempio per l'enumerazione di utenti, gruppi o altre risorse della directory con Microsoft Graph.
>  - L' **accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti della directory (più restrittivo),** impostazioni significa che gli utenti guest possono accedere solo agli oggetti della directory.
>
>Per altre informazioni, vedere [Cosa sono le autorizzazioni utente predefinite in Azure Active Directory?](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>Argomenti correlati

[Abbandonare un'organizzazione come utente Guest](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)
