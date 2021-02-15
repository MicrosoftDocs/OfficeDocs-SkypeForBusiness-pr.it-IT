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
description: È possibile selezionare i database da creare per la distribuzione. Per impostazione predefinita, il database verrà creato nel SQL Server definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base al SQL Server in cui vengono posizionati i database.
ms.openlocfilehash: 4d7a6e4f67dd6b97c8f5f837589af7b096da50b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835716"
---
# <a name="install-and-create-databases"></a>Installare e creare un database

È possibile selezionare i database da creare per la distribuzione. Per impostazione predefinita, il database verrà creato nel SQL Server definito nel sito definito e distribuirà e configurerà automaticamente i file di database in base al SQL Server in cui vengono posizionati i database.

 **Selezionare i database da creare**: selezionare la casella di controllo di ogni database che si intende distribuire e configurare. Selezionare la casella di controllo relativa a tutti i database da distribuire.

> [!CAUTION]
> Il SQL Server deve essere già stato configurato per l'istanza (se presente) e le porte del firewall devono essere aperte per supportare l'istanza in cui si stanno distribuendo i database. Per informazioni dettagliate, vedere [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)

 **Avanzate:** fare clic sul SQL Server  e fare clic sul pulsante Avanzate per scegliere le opzioni per i percorsi dei file di database nella SQL Server. Per informazioni dettagliate sul posizionamento avanzato dei file di database, vedere [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)

 **Indietro**: fare clic su questo pulsante per tornare alla schermata precedente. Il pulsante potrebbe non essere sempre disponibile, a seconda di come si è arrivati a questa finestra di dialogo.

 **Avanti**: fare clic su questo pulsante per eseguire il commit delle opzioni selezionate nella finestra di dialogo corrente e passare alla finestra di dialogo successiva per configurare ulteriori informazioni.

 **Annulla**: fare clic su questo pulsante per uscire dalla configurazione e rimuovere le modifiche. Alcune, ma non tutte, le schermate di configurazione chiedono se di desidera uscire e annullare le modifiche. Se **si seleziona Sì,** la configurazione corrente verrà chiusa e verrà restituito a Generatore di topologie. Scegliere **No** per tornare alla finestra di dialogo di configurazione corrente e continuare la configurazione.

 **?**: fare clic sul pulsante **?** per visualizzare le informazioni della Guida associate alla finestra di dialogo di configurazione corrente.


