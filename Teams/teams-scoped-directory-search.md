---
title: Usare la ricerca nella directory con ambito di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare la ricerca di directory con ambito Microsoft teams per creare visualizzazioni personalizzate della directory.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b06e675e93dd022847fc7af202045c3ecdebe63
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341778"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usare la ricerca nella directory con ambito di Microsoft Teams

La ricerca di directory con ambito Microsoft teams consente alle organizzazioni di creare confini virtuali che controllano in che modo gli utenti possono trovare e comunicare con altri utenti all'interno dell'organizzazione. 

Microsoft teams consente alle organizzazioni di creare visualizzazioni personalizzate della directory per gli utenti. Microsoft teams USA i [criteri di barriera delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) per supportare queste visualizzazioni personalizzate. Dopo l'abilitazione dei criteri, i risultati restituiti dalle ricerche di altri utenti, ad esempio per avviare una chat o per aggiungere membri a un team, verranno assegnati a un ambito secondo i criteri configurati. Gli utenti non potranno cercare o individuare i team quando è attiva la ricerca con ambito. 

> [!NOTE]
> In ambienti ibridi di Exchange questa funzionalità funziona solo con le cassette postali di Exchange Online e non con le cassette postali locali.

## <a name="when-should-you-use-scoped-directory-searches"></a>Quando è consigliabile usare ricerche di directory con ambito?

Gli scenari che traggono vantaggio dalle ricerche di directory con ambito sono simili a quelli degli scenari dei criteri Rubrica. Ad esempio, potresti voler usare la ricerca di directory con ambito nelle situazioni seguenti:

- L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate. 
- L'istituto di istruzione vuole limitare le chat tra docenti e studenti. 
 
Per informazioni su come usare i criteri Rubrica, leggere i [criteri di barriera delle informazioni in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).

> [!IMPORTANT]
> I criteri della rubrica prevedono solo una separazione virtuale degli utenti dal punto di vista della directory. Gli utenti possono comunque avviare comunicazioni con altre persone fornendo indirizzi di posta elettronica completi. È anche importante notare che tutti i dati degli utenti già memorizzati nella cache, prima dell'applicazione di criteri per la rubrica nuovi o aggiornati, rimarranno disponibili per un massimo di 30 giorni.

## <a name="turn-on-scoped-directory-search"></a>Attivare la ricerca di directory con ambito

1. Usare i criteri di barriera delle informazioni per configurare l'organizzazione in sottogruppi virtuali. Per altre informazioni, vedere [definire i criteri di barriera delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).

2. Nell'interfaccia di amministrazione di Microsoft teams selezionare impostazioni per i**Team**di **Impostazioni** > a livello di organizzazione.

3. In **ricerca**, accanto a **ricerca directory ambito in teams con i criteri di Rubrica di Exchange (SOA)**, attivare l' **attivazione.**

    ![Ricerca di directory con ambito nell'interfaccia di amministrazione di Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Questa modifica può richiedere fino a 24 ore per la replica.
