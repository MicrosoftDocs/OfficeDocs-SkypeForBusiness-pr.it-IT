---
title: Barriere di informazioni e canali condivisi (anteprima)
description: Questo articolo spiega in che modo le barriere di informazione Microsoft Teams supportano i canali condivisi
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712131"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Barriere di informazioni e canali condivisi (anteprima)

[I canali](shared-channels.md) condivisi in Microsoft Teams creare spazi di collaborazione in cui è possibile invitare persone che non sono nel team. [Le barriere alle](/microsoft-365/compliance/information-barriers) informazioni sono criteri che possono essere implementati per limitare e impedire a utenti e gruppi di comunicare tra loro all'interno e all'esterno dell'organizzazione.

I canali condivisi sono abilitati per impostazione predefinita in Teams. È possibile scegliere se le persone possono creare canali condivisi, se possono condividerli con persone esterne all'organizzazione e se possono partecipare a canali condivisi esterni creando criteri di canale. Quando i criteri di barriere alle informazioni sono configurati nell'organizzazione, i controlli vengono eseguiti durante la configurazione dei canali condivisi per verificare che nessuno dei membri del canale esistenti e i nuovi utenti aggiunti al canale condiviso violino le condizioni dei criteri delle barriere alle informazioni.

Usare la tabella seguente per comprendere in che modo i criteri di barriere alle informazioni possono influire sulle comunicazioni e provocare comportamenti specifici durante la configurazione dei canali condivisi:

|**Scenario**|**Comportamento delle barriere alle informazioni**|
|:-----------|:--------------------------------|
| **Condividere un canale con un utente dell'organizzazione** | Se l'utente non è autorizzato a comunicare con i membri del canale condiviso in base a un criterio di barriere alle informazioni, l'utente non viene visualizzato nella ricerca dell'utente e il canale non viene condiviso con il team. <br><br> Se l'utente non può essere aggiunto per un criterio di barriere alle informazioni, verrà visualizzato il messaggio seguente: Non sono state *trovate corrispondenze. Parlare con l'amministratore IT sull'espansione dell'ambito della ricerca.* |
| **Condividere un canale nell'organizzazione con un altro team di cui si è proprietari** | Se l'altro team ha utenti che non sono autorizzati a comunicare con i membri del canale condiviso in base a un criterio di barriere alle informazioni, il canale non viene condiviso con il team. <br><br> Se le comunicazioni non sono consentite per un criterio di barriere alle informazioni, verrà visualizzato il messaggio seguente: Il canale non può *essere condiviso con questo team. Selezionare un altro team o contattare l'amministratore per altre informazioni.* |
| **Condividere un canale dell'organizzazione con un altro team di cui non si è proprietari** | Se il proprietario del team o qualsiasi utente dell'altro team non è autorizzato a comunicare con i membri del canale condiviso in base a un criterio di barriere alle informazioni, il canale non può essere condiviso con il team. <br><br> Se le comunicazioni non sono consentite per un criterio di barriere alle informazioni, verrà visualizzato il messaggio seguente: Il canale non può *essere condiviso con questo team. Selezionare un altro team o contattare l'amministratore per altre informazioni.* |
| **Aggiungere un nuovo utente al team quando il team ha condiviso canali con altri team** | Se il nuovo utente non è autorizzato a comunicare con i membri del team del canale condiviso in base a un criterio di barriere alle informazioni, l'utente non può essere aggiunto al team. Quando si aggiunge un utente a un team con sei o più canali condivisi, l'utente viene immediatamente aggiunto al canale e la condivisione è supportata. La condivisione per il team e i canali condivisi in precedenza può essere interrotta se il nuovo utente risulta non conforme a un criterio di barriere alle informazioni.<br><br> Se non è possibile aggiungere l'utente per un criterio di barriere alle informazioni, verrà visualizzato il messaggio seguente: Impossibile aggiungere l'utente a causa di un criterio *di barriere alle informazioni.* |
| **Condividere un canale con un team esterno** | I criteri di barriere alle informazioni nei tenant interni ed esterni non limitano le comunicazioni tra gli utenti dei diversi tenant. I canali condivisi sono disponibili per essere condivisi con utenti esterni. |
