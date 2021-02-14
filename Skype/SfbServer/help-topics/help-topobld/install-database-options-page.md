---
title: Pagina delle opzioni Installa database
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'È possibile configurare opzioni avanzate per il posizionamento dei file di database e di registro nel SQL Server. Le opzioni disponibili sono:'
ms.openlocfilehash: f9c2553fb0a4fa8f538a70a2ce496eaf054a0dc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806916"
---
# <a name="install-database-options-page"></a>Pagina delle opzioni Installa database

È possibile configurare opzioni avanzate per il posizionamento dei file di database e di registro nel SQL Server. Le opzioni disponibili sono:

> [!IMPORTANT]
> Selezionare l'opzione più adatta ai requisiti e ai criteri relativi al posizionamento dei file di dati e di registro nei SQL Server computer.

 **Determina automaticamente** il percorso dei file di database: l'opzione predefinita utilizza un algoritmo che determina lo spazio disponibile nel SQL Server e distribuisce i file di database e di registro per ottenere prestazioni ottimali.

 **Utilizzare SQL Server predefinite dell'istanza:** selezionare questa opzione per posizionare i file di database e di registro in base alle impostazioni dell'istanza in SQL Server. Le opzioni vengono in genere gestite e configurate dall'amministratore del database.

 **Ecco il percorso** nel SQL Server di destinazione: selezionare questa opzione per definire i propri percorsi per i file di registro e di database di SQL Server digitando il percorso completo dell'unità e della cartella in cui verranno inseriti il database e i file di registro.

> [!IMPORTANT]
> I percorsi immessi possono essere modificati in base agli algoritmi di ottimizzazione delle prestazioni nell'installazione. Per informazioni dettagliate, vedere [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: fare clic su OK per eseguire il commit delle modifiche.

 **Annulla**: fare clic su Annulla per rimuovere le modifiche e tornare alla schermata Installa database.

 **?**: fare clic su ? per accedere a questa pagina della Guida.

## <a name="see-also"></a>Vedere anche

[Posizionamento dei file di registro e dei file di dati di SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
