---
title: Installare Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: "Riepilogo: informazioni su come preparare l'ambiente per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042383"
---
# <a name="install-skype-for-business-server"></a>Installare Skype for Business Server
 
**Riepilogo:** Informazioni su come preparare l'ambiente per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Indirizzo:.
  
In questo articolo viene illustrata l'installazione di un esempio di Skype for Business Server. In questo articolo non viene eseguito il tentativo di coprire tutte le procedure necessarie per eseguire un'installazione completa di Skype for Business Server. L'obiettivo è quello di fornire procedure di esempio in una topologia definita in modo restrittivo, che include la funzionalità di base per la riunione e la condivisione.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Panoramica del processo di installazione per Skype for Business Server

Un'installazione di Skype for Business Server include molte procedure diverse. Le procedure necessarie per ottenere Skype for Business Server in esecuzione nel proprio ambiente dipendono dalle specifiche dell'ambiente in uso. Ad esempio, se si utilizza Windows Server per DNS, è possibile usufruire della procedura di esempio per l'aggiunta di una voce DNS. Se si utilizza un altro sistema per DNS, è necessario seguire le procedure per il sistema DNS specifico. Questo è vero per molte delle procedure descritte in questa sezione.
  
Skype for Business Server è disponibile in Standard Edition ed Enterprise Edition. La differenza principale è che Standard Edition non supporta le funzionalità di disponibilità elevata incluse in Enterprise Edition. 
  
Skype for Business Server è un prodotto avanzato e l'esatta procedura di installazione dipende molto dalle circostanze specifiche. In questa sezione vengono illustrati i passaggi generali da eseguire per installare il prodotto. Tuttavia, ogni procedura potrebbe essere diversa in base all'ambiente e alle decisioni di pianificazione. Ad esempio, per le organizzazioni di piccole dimensioni un singolo server che esegue Skype for Business Server Standard Edition potrebbe essere appropriato, mentre una vasta organizzazione multinazionale potrebbe avere 50 server nelle posizioni di tutto il mondo dedicate al prodotto.
  
> [!NOTE]
> Per ulteriori informazioni sugli aggiornamenti cumulativi più recenti, vedere [Updates for Skype for Business Server](https://support.microsoft.com/kb/3061064). Dopo l'installazione della patch di CU1, un amministratore deve `Update-CsAdminRole` eseguire il cmdlet. Questo cmdlet è necessario per accedere ai nuovi cmdlet di GCP su Remote PowerShell.
  
> [!IMPORTANT]
> Le procedure descritte in questa sezione fungono da esempio per l'utilizzo di un insieme di requisiti definito in modo restrittivo e sono già state apportate decisioni specifiche. Le procedure effettive che è necessario installare in Skype for Business Server saranno probabilmente molto diverse. Utilizzare le procedure descritte in questa sezione solo come esempio e non come guida dettagliata per l'installazione di Skype for Business Server in ogni ambiente. 
  
Ottenere Skype for Business Server attivo e funzionante per la prima volta comporta otto passaggi principali. È necessario capire che le procedure di esempio in questa sezione non sono le uniche procedure necessarie per l'installazione di Skype for Business Server. Gli otto passaggi seguenti sono semplicemente esempi che consentono di comprendere meglio il processo generale e di ottenere un ambiente di lavoro di base attivo e funzionante. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come indicato nel diagramma. Gli otto passaggi sono i seguenti:
  
![Panoramica del processo di installazione.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installare i prerequisiti per Skype for Business Server](install-prerequisites.md) : installare i prerequisiti su tutti i server che compongono la topologia di Skype for Business Server. Si noti che i prerequisiti non sono gli stessi per tutti i ruoli. Ad esempio, i server che forniscono il ruolo front-end dispongono di un set di prerequisiti e i server che forniscono un ruolo di Director dispongono di un set di prerequisiti diverso. Per ulteriori informazioni, vedere documentazione sulla pianificazione prerequisita.
    
- [Creare una condivisione file in Skype for Business Server](create-a-file-share.md) : creare una condivisione file che verrà utilizzata dai server nella topologia di Skype for Business Server.
    
- [Installare gli strumenti di amministrazione in Skype for Business Server](install-administrative-tools.md) : gli strumenti di amministrazione includono il generatore di topologie e il pannello di controllo. È necessario installare gli strumenti di amministrazione in almeno un server nella topologia o in una workstation di gestione a 64 bit che esegue una versione del sistema operativo Windows supportata per Skype for Business Server.
    
- [Preparare Active Directory per Skype for Business Server](prepare-active-directory.md) : Skype for Business Server è compatibile con Active Directory. È necessario preparare il dominio di Active Directory per l'utilizzo con Skype for Business Server. È possibile eseguire questa operazione tramite la distribuzione guidata e viene eseguita una sola volta per il dominio. Ciò è dovuto al fatto che il processo crea gruppi e modifica il dominio ed è necessario farlo solo una volta.
    
- [Creare record DNS per Skype for Business Server](create-dns-records.md) : affinché Skype for Business Server funzioni correttamente, è necessario disporre di un numero di impostazioni DNS. In questo modo i client sapranno come accedere ai servizi e i server conoscono l'uno dell'altro. Queste impostazioni devono essere completate solo una volta per ogni distribuzione perché, una volta assegnata una voce DNS, è disponibile in tutto il dominio.
    
- [Creare e pubblicare una nuova topologia in Skype for Business Server](create-and-publish-new-topology.md) : prima di poter installare il sistema Skype for Business Server in ognuno dei server della topologia, è necessario creare una topologia e pubblicarla. Quando si pubblica una topologia, vengono caricate le informazioni sulla topologia nel database dell'archivio di gestione centrale. Se si tratta di un pool Enterprise Edition, si sta creando il database dell'archivio di gestione centrale al primo avvio della pubblicazione di una nuova topologia. Se si tratta di Standard Edition, è necessario eseguire il processo di preparazione del primo server Standard Edition dalla distribuzione guidata prima di pubblicare una topologia. Questo preparato per Standard Edition installando un'istanza di SQL Server Express Edition e creando l'archivio di gestione centrale.
    
- [Installare Skype for Business Server nei server nella topologia](install-skype-for-business-server.md) : dopo che la topologia è stata caricata nell'archivio di gestione centrale e Active Directory conosce i server che eseguiranno i ruoli, è necessario installare il sistema Skype for Business Server in ognuno dei server della topologia.
    
- [Verificare la topologia in Skype for Business Server](verify-the-topology.md) : dopo aver pubblicato la topologia e i componenti di sistema di Skype for Business Server installati in ognuno dei server della topologia, è possibile verificare che la topologia funzioni come previsto. Ciò include la verifica che la configurazione si è propagata a tutti i server di Active Directory in modo che l'intero dominio sappia che Skype for business è disponibile nel dominio.
    

