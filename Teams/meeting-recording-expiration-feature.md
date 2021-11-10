---
title: Caratteristica di scadenza della registrazione della riunione
author: cichur
ms.author: v-cichur
ms.reviewer: ''
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Informazioni sulla funzionalità di scadenza della registrazione della riunione in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfbbc8602044c0429de414b94b88d0e0e5aa8b19
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889526"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Caratteristica di scadenza della registrazione delle riunioni - Domande frequenti

**Qual modifica verrà effettuata?**

Stiamo introducendo un'impostazione di scadenza predefinita  di 60 giorni per tutte le registrazioni Teams riunione (TMR) appena create. Questa opzione è attivata per impostazione predefinita per tutti i tenant ed è necessario disattivarla se non si vuole usare questa caratteristica. Il OneDrive e SharePoint monitorerà la data di scadenza impostata in tutti i TMR e sposterà automaticamente i TMR nel Cestino alla data di scadenza.

**Perché stiamo introducendo questa modifica?**

Abbiamo risposto alle tue richieste per la funzionalità di scadenza della registrazione della riunione. Si tratta di un meccanismo di pulizia leggero per ridurre i disordini di archiviazione creati da TMR a freddo. In media, il 99% dei TMR non viene mai riwatchato dopo 60 giorni.

**Perché questa opzione verrà attivata per impostazione predefinita?**

Riteniamo che quasi tutti i clienti trarranno vantaggio dalla riduzione del carico di archiviazione nel tenant rimuovendo le registrazioni che probabilmente non verranno mai riguardate dopo 60 giorni. Il nostro obiettivo è offrire un'esperienza il più pulita possibile a tutti i clienti per impostazione predefinita.

**Come viene calcolata la data di scadenza?**

La data di scadenza viene calcolata come giorno di creazione più il numero predefinito di giorni impostato nei criteri di Teams dall'amministratore.

**Come può un amministratore modificare la data di scadenza?**

Gli amministratori possono modificare l'impostazione di scadenza predefinita nella console Teams criteri. Questa modifica avrà effetto solo sui TMR appena creati da quel momento in poi. Non inciderà sulle registrazioni prima di tale data.

Gli amministratori non possono modificare la data di scadenza nei TMR esistenti. Questa operazione viene eseguita per proteggere la decisione dell'utente proprietario del TMR.

**Quali sono le conseguenze di questo impatto?**

Chiunque archivia TMR in OneDrive o SharePoint.

**Perché è consigliabile usare questa funzionalità?**

Questa funzionalità è attivata per impostazione predefinita. Per disabilitarla, modificare l'impostazione di scadenza predefinita nella console dei criteri di Teams su **Nessuna scadenza.**
È consigliabile usare questa opzione per limitare il consumo OneDrive o Sharepoint per lo spazio di archiviazione nel cloud basato sui record Teams riunioni. Una tipica registrazione della riunione consuma circa 400 MB all'ora di registrazione.

**È consigliabile affidarsi a questa caratteristica per una rigorosa conformità alla sicurezza e alla conformità?**

No, non è consigliabile affidarsi a questa opzione per la protezione legale, perché gli utenti finali possono modificare la data di scadenza di tutte le registrazioni che controllano.

**I criteri di conservazione e/o eliminazione impostati nel Centro sicurezza & conformità sovrascrivono l'impostazione di scadenza della registrazione Teams riunione?**

Sì, tutti i criteri impostati nel Centro conformità avranno la precedenza completa.

Ad esempio:

- Se si dispone di un criterio che indica che tutti i file di un sito devono essere conservati per 100 giorni e che l'impostazione di scadenza per la registrazione di una riunione di Teams è 30 giorni, la registrazione verrà mantenuta per tutti i 100 giorni.
- Se si dispone di un criterio di eliminazione che indica che tutte le registrazioni delle riunioni di Teams verranno eliminate dopo cinque giorni e si ha un'impostazione di scadenza per una registrazione di una riunione di Teams di 30 giorni, la registrazione verrà eliminata dopo cinque giorni.

**Cosa succede alla scadenza di un TMR?**

Alla data di scadenza, la registrazione viene spostata nel Cestino e il campo della data di scadenza viene deselezionato. Se si recupera la registrazione dal Cestino, questa funzionalità non verrà eliminata di nuovo perché la data di scadenza è stata cancellata.

**In che modo ricevo una notifica sulla scadenza del file?**

- Tutti gli utenti riceveranno una notifica relativa alla data di scadenza nell'elenco di controllo della registrazione nella finestra Teams chat.
- Tutti gli utenti con accesso in visualizzazione vedranno un'icona rossa accanto al file nella cartella OneDrive o SharePoint 14 giorni prima della scadenza del file.
- Il proprietario del file riceverà una notifica tramite posta elettronica alla scadenza della registrazione e verrà indirizzato al Cestino per recuperare la registrazione.

**Quali SKU sono necessari per questa funzionalità?**

- Per impostazione predefinita, tutti gli SKU avranno questa funzionalità.

- Per impostazione predefinita, tutti gli utenti avranno un periodo di scadenza di 30 giorni e non potranno modificare la data di scadenza.

**La scadenza del file è un evento controllato e sarà possibile visualizzarlo nei log di audit?**

Sì, questi verranno visualizzati come eventi di eliminazione del sistema nel log di controllo.

**Cosa succede se si vuole che l'amministratore abbia il controllo completo sul ciclo di vita delle registrazioni delle riunioni e non si voglia offrire agli utenti finali la possibilità di ignorare la data di scadenza?**

È consigliabile usare i criteri di conservazione e/o eliminazione di sicurezza e conformità disponibili nell'ambito dello SKU di conformità E5. Questa offerta è destinata a risolvere problemi legali amministrativi complessi e basati sul contratto di servizio.

Questa caratteristica è pensata esclusivamente come meccanismo di pulizia leggero per ridurre i disordini di archiviazione creati dalle registrazioni Teams riunioni a freddo.

**Quando verrà eliminato il file?**

Il file verrà eliminato entro cinque giorni dalla data di scadenza, anche se non si tratta di una garanzia rigorosa.
