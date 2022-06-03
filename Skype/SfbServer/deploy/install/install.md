---
title: Installare Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: "Riepilogo: informazioni su come preparare l'ambiente per un'installazione di Skype for Business Server."
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860587"
---
# <a name="install-skype-for-business-server"></a>Installare Skype for Business Server
 
**Riepilogo:** Informazioni su come preparare l'ambiente per un'installazione di Skype for Business Server.
  
Questo articolo illustra un'installazione di esempio di Skype for Business Server. Questo articolo non tenta di coprire tutte le procedure necessarie per eseguire un'installazione completa Skype for Business Server. L'obiettivo è fornire procedure di esempio in una topologia definita in modo ristretto che include funzionalità di base di meet-and-share.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Panoramica del processo di installazione per Skype for Business Server

Un'installazione di Skype for Business Server include molte procedure diverse. Le procedure necessarie per eseguire Skype for Business Server nell'ambiente dipendono dalle specifiche dell'ambiente. Ad esempio, se si usa Windows Server per DNS, si trarrà vantaggio dalla procedura di esempio per l'aggiunta di una voce DNS. Se si usa un altro sistema per DNS, è necessario seguire le procedure per il sistema DNS specifico. Questo vale per molte delle procedure descritte in questa sezione.
  
Skype for Business Server è disponibile in edizione Standard e edizione Enterprise. La differenza principale è che edizione Standard non supporta le funzionalità a disponibilità elevata incluse in edizione Enterprise. 
  
Skype for Business Server è un prodotto avanzato e il processo di installazione esatto dipende molto dalle circostanze specifiche. Questa sezione illustra i passaggi generali per installare il prodotto. Tuttavia, ogni procedura potrebbe essere diversa a seconda dell'ambiente e delle decisioni di pianificazione. Per le organizzazioni di piccole dimensioni, ad esempio, un singolo server potrebbe essere appropriato eseguire Skype for Business Server edizione Standard, mentre una grande organizzazione multinazionale potrebbe avere 50 server in località in tutto il mondo dedicati al prodotto.
  
> [!NOTE]
> Per informazioni sugli aggiornamenti cumulativi più recenti, vedere [Aggiornamenti per Skype for Business Server](https://support.microsoft.com/kb/3061064). Dopo aver installato la patch CU1, un amministratore deve eseguire il  `Update-CsAdminRole` cmdlet. Questo cmdlet è necessario per accedere ai nuovi cmdlet GCP tramite PowerShell remoto.
  
> [!IMPORTANT]
> Le procedure descritte in questa sezione sono un esempio dell'uso di un set ristretto di requisiti e presuppongono che siano già state prese decisioni specifiche. Le procedure effettive necessarie per installare Skype for Business Server saranno probabilmente molto diverse. Usare le procedure in questa sezione solo come esempio e non come guida dettagliata per l'installazione di Skype for Business Server in ogni ambiente. 
  
L'avvio e l'esecuzione di Skype for Business Server per la prima volta prevede otto passaggi principali. È necessario comprendere che le procedure di esempio in questa sezione non sono le uniche procedure necessarie per l'installazione di Skype for Business Server. Gli otto passaggi seguenti sono semplicemente esempi che consentono di comprendere meglio il processo complessivo e di ottenere un ambiente di lavoro di base attivo e in esecuzione. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come descritto nel diagramma. Gli otto passaggi sono:
  
![Panoramica del processo di installazione.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installare i prerequisiti per Skype for Business Server](install-prerequisites.md): installare i prerequisiti in tutti i server che costituiscono la topologia Skype for Business Server. Si noti che i prerequisiti non sono uguali per tutti i ruoli. Ad esempio, i server che forniscono il ruolo front-end hanno un set di prerequisiti e i server che forniscono un ruolo director hanno un set diverso di prerequisiti. Per altri dettagli, vedere la documentazione relativa alla pianificazione dei prerequisiti.
    
- [Creare una condivisione file in Skype for Business Server](create-a-file-share.md): creare una condivisione file che verrà usata dai server in tutta la topologia Skype for Business Server.
    
- [Installare gli strumenti di amministrazione in Skype for Business Server](install-administrative-tools.md) : gli strumenti di amministrazione includono Generatore di topologie e Pannello di controllo. È necessario installare gli strumenti di amministrazione in almeno un server nella topologia o in una workstation di gestione a 64 bit che esegue una versione del sistema operativo Windows supportata per Skype for Business Server.
    
- [Preparare Active Directory per Skype for Business Server](prepare-active-directory.md) : Skype for Business Server funziona a stretto contatto con Active Directory. È necessario preparare il dominio di Active Directory per l'uso con Skype for Business Server. È possibile eseguire questa operazione tramite la Distribuzione guidata ed è stata eseguita una sola volta per il dominio. Questo avviene perché il processo crea gruppi e modifica il dominio ed è necessario eseguire questa operazione una sola volta.
    
- [Creare record DNS per Skype for Business Server](create-dns-records.md): affinché Skype for Business Server funzioni correttamente, è necessario che siano presenti diverse impostazioni DNS. In questo modo i client sanno come accedere ai servizi e i server sono a conoscenza tra loro. Queste impostazioni devono essere completate solo una volta per ogni distribuzione perché dopo aver assegnato una voce DNS, è disponibile in tutto il dominio.
    
- [Creare e pubblicare una nuova topologia in Skype for Business Server](create-and-publish-new-topology.md) : prima di poter installare il sistema Skype for Business Server in ogni server della topologia, è necessario creare una topologia e pubblicarla. Quando si pubblica una topologia, si caricano le informazioni sulla topologia nel database dell'archivio di gestione centrale. Se si tratta di un pool di edizione Enterprise, si crea il database dell'archivio di gestione centrale la prima volta che si pubblica una nuova topologia. Se si tratta di edizione Standard, è necessario eseguire il processo Prepare First edizione Standard Server dalla Distribuzione guidata prima di pubblicare una topologia. Questa operazione si prepara per edizione Standard installando un'istanza di SQL Server Express Edition e creando l'archivio di gestione centrale.
    
- [Installare Skype for Business Server nei server nella topologia](install-skype-for-business-server.md): dopo aver caricato la topologia nell'archivio di gestione centrale e Active Directory è a conoscenza dei server che eseguiranno i ruoli, è necessario installare il sistema Skype for Business Server in ognuno dei server della topologia.
    
- [Verificare la topologia in Skype for Business Server](verify-the-topology.md) : dopo aver pubblicato la topologia e i componenti di sistema Skype for Business Server installati in ognuno dei server della topologia, è possibile verificare che la topologia funzioni come previsto. Ciò include la verifica che la configurazione sia stata propagata a tutti i server Active Directory in modo che l'intero dominio sappia che Skype for Business è disponibile nel dominio.
    

