---
title: Funzionalità di scadenza della registrazione delle riunioni
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
ms.openlocfilehash: 67cbef7e6fad2c9620de17f89b8b3a4fe641368e
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853227"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Funzionalità di scadenza della registrazione delle riunioni - Domande frequenti

**Qual modifica verrà effettuata?**

Stiamo introducendo un'impostazione di scadenza predefinita di 120 giorni per *tutte le* registrazioni delle riunioni di Teams (TTR) appena create. Questa funzionalità è attivata per impostazione predefinita per tutti i tenant ed è necessario disattivarla se non si vuole usare questa funzionalità. Il sistema OneDrive e SharePoint monitorerà la data di scadenza impostata in tutti i TMR e sposterà automaticamente ITR nel Cestino alla data di scadenza.

**Perché stiamo introducendo questa modifica?**

Abbiamo risposto alle tue richieste per la funzionalità di scadenza della registrazione della riunione. Si tratta di un meccanismo di pulizia leggero per ridurre il disordine di archiviazione creato da TMR freddo. In media, il 99% delle TR non viene mai aggiornato dopo 120 giorni.

**Perché questa opzione verrà attivata per impostazione predefinita?**

Siamo convinti che quasi tutti i clienti beneficeranno della riduzione del carico di archiviazione nel tenant rimuovendo le registrazioni che probabilmente non verranno più sottoposte a controllo dopo 120 giorni. Il nostro obiettivo è fornire un'esperienza il più pulita possibile per tutti i clienti per impostazione predefinita.

**Come viene calcolata la data di scadenza?**

La data di scadenza viene calcolata come giorno di creazione più il numero predefinito di giorni impostato nel criterio di Teams dall'amministratore.

**In che modo un amministratore può modificare la data di scadenza?**

Gli amministratori possono modificare l'impostazione di scadenza predefinita nella console dei criteri di Teams. Da quel momento in poi tale modifica avrà effetto solo sulle nuove TR create. Non influirà su registrazioni precedenti a tale data.

Gli amministratori non possono modificare la data di scadenza nei TMR esistenti. Questo viene fatto per proteggere la decisione dell'utente che possiede il TMR.

**Chi ha questo impatto?**

Chiunque archivii ITR in OneDrive o SharePoint.

**Perché è consigliabile usare questa funzionalità?**

Questa funzionalità è attivata per impostazione predefinita. Per disabilitarla, modifica l'impostazione predefinita di scadenza nella console dei criteri di Teams su **Nessuna scadenza**.
Usare questa opzione per limitare il consumo di OneDrive o Sharepoint per l'archiviazione cloud basato sui record delle riunioni Teams. Una registrazione tipica di una riunione richiede circa 400 MB all'ora di registrazione.

**Devo fare affidamento su questa funzionalità per una stretta adesione alla sicurezza e alla conformità?**

No, non è consigliabile affidarsi a questa opzione per la protezione legale in quanto gli utenti finali possono modificare la data di scadenza di tutte le registrazioni che controllano.

**I criteri di conservazione e/o di eliminazione impostati nel Centro sicurezza & conformità sostituiscono l'impostazione di scadenza della registrazione della riunione Teams?**

Sì, tutti i criteri impostati nel Centro conformità avranno la precedenza.

Ad esempio:

- Se è stato impostato un criterio che indica che tutti i file in un sito devono essere conservati per 100 giorni e l'impostazione di scadenza per una Teams la registrazione della riunione è di 30 giorni, la registrazione verrà mantenuta per 100 giorni.
- Se sono presenti criteri di eliminazione che informano che tutte le registrazioni di Teams riunione verranno eliminate dopo cinque giorni e si ha un'impostazione di scadenza per una Teams registrazione di una riunione di 30 giorni, la registrazione verrà eliminata dopo cinque giorni.

**Cosa succede quando scade un TMR?**

Alla data di scadenza, la registrazione viene spostata nel Cestino e il campo della data di scadenza viene cancellato. Se si recupera la registrazione dal Cestino, non verrà eliminata di nuovo da questa funzionalità perché la data di scadenza è stata cancellata.

**In che modo ricevo una notifica sulla scadenza del file?**

- Tutti gli utenti visualizzeranno una notifica sulla data di scadenza nell'elenco di controllo per la registrazione nella finestra Teams chat.
- Tutti gli utenti con accesso in visualizzazione vedranno un'icona rossa accanto al file nella cartella OneDrive o SharePoint 14 giorni prima della scadenza del file.
- Il proprietario del file riceverà una notifica tramite posta elettronica alla scadenza della registrazione e verrà indirizzato al Cestino per recuperare la registrazione.

**Quali SKU sono necessari per questa funzionalità?**

- Per impostazione predefinita, tutti gli SKU avranno questa funzionalità.

- Per impostazione predefinita, gli utenti A1 scadranno di 30 giorni e non potranno modificare la data di scadenza.

**La scadenza del file è un evento controllato e sarà possibile visualizzarlo nei log di audit?**

Sì, verranno visualizzati come eventi di eliminazione del sistema nel log di controllo.

**Cosa succede se si vuole che l'amministratore abbia il controllo completo sul ciclo di vita delle registrazioni delle riunioni e non si voglia offrire agli utenti finali la possibilità di ignorare la data di scadenza?**

È consigliabile usare i criteri di conservazione e/o eliminazione della sicurezza e/o dell'eliminazione disponibili nell'ambito dello SKU di conformità E5. Questa offerta è destinata a risolvere problemi legali amministrativi complessi e basati sul contratto di servizio.

Questa caratteristica è pensata esclusivamente come un meccanismo di pulizia leggero per ridurre il disordine di archiviazione creato dalle registrazioni di riunioni a freddo Teams.

**Quando verrà eliminato il file?**

Il file verrà eliminato entro cinque giorni dalla data di scadenza, anche se questa non è una garanzia rigorosa.

**La scadenza predefinita è di 120 giorni, ma quando si seleziona Teams'interfaccia di amministrazione sono 60 giorni. Perché?**

Il modo in cui funzionano i criteri di Teams è che se un criterio nel centro è impostato dall'amministratore, viene creato uno snapshot memorizzato nella cache di tutte le impostazioni. Se l'amministratore ha impostato un attributo per il criterio quando è stato temporaneamente configurato un valore predefinito di 60 giorni, dovrà impostarlo manualmente su 120 giorni. Se non avevano un'impostazione personalizzata prima di impostare l'impostazione predefinita di 120 giorni, ricevono i 120 giorni.
