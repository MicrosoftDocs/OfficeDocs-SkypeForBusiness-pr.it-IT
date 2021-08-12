---
title: Installare e creare un database
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile selezionare i database da creare per la distribuzione. Per impostazione predefinita, il database verrà creato nel SQL Server definito nel sito definito e verrà distribuito e configurato automaticamente i file di database in base al SQL Server in cui si stanno posizionando i database.
ms.openlocfilehash: 68848c644140d4bea4ec23bbf356da62d85eb6291cab4c7001e66879fe6e6088
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279034"
---
# <a name="install-and-create-databases"></a>Installare e creare un database

È possibile selezionare i database da creare per la distribuzione. Per impostazione predefinita, il database verrà creato nel SQL Server definito nel sito definito e verrà distribuito e configurato automaticamente i file di database in base al SQL Server in cui si stanno posizionando i database.

 **Selezionare i database da creare**: selezionare la casella di controllo di ogni database che si intende distribuire e configurare. Selezionare la casella di controllo relativa a tutti i database da distribuire.

> [!CAUTION]
> Il SQL Server deve essere già stato configurato per l'istanza (se presente) e le porte del firewall devono essere aperte per supportare l'istanza in cui si distribuiscono i database. Per informazioni dettagliate, vedere [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Avanzate**: fare clic sul SQL Server  e fare clic sul pulsante Avanzate per scegliere le opzioni per i percorsi dei file di database SQL Server. Per informazioni dettagliate sul posizionamento avanzato dei file di database, vedere [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)

 **Indietro**: fare clic su questo pulsante per tornare alla schermata precedente. Il pulsante potrebbe non essere sempre disponibile, a seconda di come si è arrivati a questa finestra di dialogo.

 **Avanti**: fare clic su questo pulsante per eseguire il commit delle opzioni selezionate nella finestra di dialogo corrente e passare alla finestra di dialogo successiva per configurare ulteriori informazioni.

 **Annulla**: fare clic su questo pulsante per uscire dalla configurazione e rimuovere le modifiche. Alcune, ma non tutte, le schermate di configurazione chiedono se di desidera uscire e annullare le modifiche. Se **si seleziona Sì,** la configurazione corrente verrà chiusa e verrà restituito a Generatore di topologie. Scegliere **No** per tornare alla finestra di dialogo di configurazione corrente e continuare la configurazione.

 **?**: fare clic sul pulsante **?** per visualizzare le informazioni della Guida associate alla finestra di dialogo di configurazione corrente.