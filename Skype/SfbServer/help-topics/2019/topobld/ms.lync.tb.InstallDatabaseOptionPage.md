---
title: Pagina delle opzioni Installa database
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'È possibile configurare opzioni avanzate per il posizionamento dei file di database e di registro nel SQL Server. Le opzioni disponibili sono:'
ms.openlocfilehash: 1dcf386be6978a8f2b3524310ff53ae7fb2be5c1b59991c13db7251d833ed341
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330190"
---
# <a name="install-database-options-page"></a>Pagina delle opzioni Installa database

È possibile configurare opzioni avanzate per il posizionamento dei file di database e di registro nel SQL Server. Le opzioni disponibili sono:

> [!IMPORTANT]
> Selezionare l'opzione più adatta ai requisiti e ai criteri relativi al posizionamento dei dati e dei file di registro nei SQL Server computer.

 **Determinare automaticamente il percorso dei file** di database: l'opzione predefinita utilizza un algoritmo che determina lo spazio disponibile nel SQL Server e distribuisce i file di database e di registro per ottenere prestazioni ottimali.

 **Use SQL Server instance defaults**: selezionare questa opzione per posizionare i file di database e i file di registro in base alle impostazioni dell'istanza in SQL Server. Le opzioni vengono in genere gestite e configurate dall'amministratore del database.

 **Us these path on target SQL Server**: Selezionare questa opzione per definire i propri percorsi per i file di database e di registro di SQL Server digitando il percorso completo dell'unità e della cartella in cui verranno inseriti il database e i file di registro.

> [!IMPORTANT]
> I percorsi immessi possono essere modificati in base agli algoritmi di ottimizzazione delle prestazioni nell'installazione. Per informazioni dettagliate, vedere [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **OK**: fare clic su OK per eseguire il commit delle modifiche.

 **Annulla**: fare clic su Annulla per rimuovere le modifiche e tornare alla schermata Installa database.

 **?**: fare clic su ? per accedere a questa pagina della Guida.

## <a name="see-also"></a>Vedere anche

[Posizionamento dei file di registro e dei file di dati di SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)