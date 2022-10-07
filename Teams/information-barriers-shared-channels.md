---
title: Barriere informative e canali condivisi (anteprima)
description: Questo articolo spiega in che modo le barriere informative in Microsoft Teams supportano i canali condivisi
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: 5b214a4c60df7b50f508fec7985c6f38b65985e6
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047216"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Barriere informative e canali condivisi (anteprima)

[I canali condivisi](shared-channels.md) in Microsoft Teams creano spazi di collaborazione in cui è possibile invitare persone che non fanno parte del team. [Microsoft Purview Information Barriers](/microsoft-365/compliance/information-barriers) sono criteri che possono essere implementati per limitare e impedire a utenti e gruppi di comunicare tra loro all'interno e all'esterno dell'organizzazione.

I canali condivisi sono abilitati per impostazione predefinita in Teams. È possibile scegliere se le persone possono creare canali condivisi, se possono condividerli con persone esterne all'organizzazione e se possono partecipare a canali condivisi esternicreando criteri di canale. Quando nell'organizzazione vengono configurati criteri di barriere alle informazioni, vengono eseguiti controlli durante la configurazione dei canali condivisi per verificare che nessuno dei membri del canale esistenti e dei nuovi utenti aggiunti al canale condiviso violi le condizioni dei criteri sulle barriere alle informazioni.

Usare la tabella seguente per comprendere in che modo i criteri di barriere alle informazioni possono influire sulle comunicazioni e generare comportamenti specifici durante la configurazione dei canali condivisi:

|**Scenario**|**Comportamento degli ostacoli alle informazioni**|
|:-----------|:--------------------------------|
| **Condividere un canale con un utente dell'organizzazione** | Se l'utente non è autorizzato a comunicare con i membri del canale condiviso in base a un criterio di barriere alle informazioni, l'utente non viene visualizzato nella ricerca utente e il canale non viene condiviso con il team. <br><br> Se non è possibile aggiungere l'utente in base a un criterio di barriere alle informazioni, verrà visualizzato il messaggio seguente: *Non sono state trovate corrispondenze. Rivolgersi all'amministratore IT per espandere l'ambito della ricerca.* |
| **Condividere un canale dell'organizzazione con un altro team di cui si è proprietari** | Se l'altro team ha utenti che non sono autorizzati a comunicare con i membri del canale condiviso in base a un criterio di barriere alle informazioni, il canale non viene condiviso con il team. <br><br> Se le comunicazioni non sono consentite in base a un criterio sugli ostacoli alle informazioni, verrà visualizzato il messaggio seguente: *Il canale non può essere condiviso con il team. Seleziona un altro team o contatta l'amministratore per altre info.* |
| **Condividere un canale dell'organizzazione con un altro team di cui non si è proprietari** | Se il proprietario del team o gli utenti dell'altro team non sono autorizzati a comunicare con i membri del canale condiviso in base a un criterio sugli ostacoli alle informazioni, il canale non può essere condiviso con il team. <br><br> Se le comunicazioni non sono consentite in base a un criterio sugli ostacoli alle informazioni, verrà visualizzato il messaggio seguente: *Il canale non può essere condiviso con il team. Seleziona un altro team o contatta l'amministratore per altre info.* |
| **Aggiungere un nuovo utente al team quando il team ha condiviso canali con altri team** | Se al nuovo utente non è consentito comunicare con i membri del team del canale condiviso in base a un criterio di barriere alle informazioni, l'utente non può essere aggiunto al team. Quando si aggiunge un utente a un team con sei o più canali condivisi, l'utente viene immediatamente aggiunto al canale e la condivisione è supportata. La condivisione per il team e i canali condivisi in precedenza può essere interrotta se il nuovo utente risulta non conforme ai criteri sulle barriere alle informazioni.<br><br> Se l'utente non può essere aggiunto in base a un criterio di barriere alle informazioni, verrà visualizzato il messaggio seguente: *Impossibile aggiungere un utente a causa di un criterio di barriere alle informazioni.* |
| **Condividere un canale con un team esterno** | I criteri sugli ostacoli alle informazioni nei tenant interni ed esterni non limitano le comunicazioni tra gli utenti dei diversi tenant. I canali condivisi sono disponibili per la condivisione con utenti esterni. |
