---
title: 'Lync Server 2013: gestione della configurazione'
description: 'Lync Server 2013: gestione della configurazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5999708811cc4a34cf846a1ddd481ba38e07c62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552152"
---
# <a name="configuration-management-in-lync-server-2013"></a>Gestione della configurazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-05-15_

La gestione della configurazione è il processo di registrazione e monitoraggio delle risorse hardware e software e delle informazioni di configurazione del sistema. Viene generalmente utilizzato per tenere conto delle licenze software, per gestire una configurazione hardware e software standard per i computer client e i server e definire gli standard di denominazione per i nuovi computer. La gestione della configurazione copre generalmente le categorie seguenti:

  - **Hardware**     In questa categoria sono riportate le apparecchiature possedute dall'organizzazione IT, in cui si trovano le apparecchiature e che utilizzano le apparecchiature. Queste informazioni consentono a un'organizzazione di pianificare e preventivare gli aggiornamenti, mantenere le build hardware standard, riportare il valore delle risorse IT a fini contabili e contribuire a prevenire il furto.

  - **Software**     Questa categoria consente di tenere traccia del software installato in ogni computer, dei numeri di versione e della posizione delle licenze. Queste informazioni aiutano a pianificare gli aggiornamenti, a garantire che il software venga concesso in licenza e a rilevare la presenza di software non autorizzato (e senza licenza).

  - **Compilazioni standard**     Questa categoria tiene traccia della build standard corrente per i computer client e i server e se i computer client e i server soddisfano questo standard. La definizione e l'applicazione di compilazioni standard consentono al personale di supporto perché il personale è tenuto a mantenere solo un numero limitato di versioni di ogni parte del software.

  - **Aggiornamenti cumulativi e hotfix**     Questa categoria tiene traccia dei Service Pack che sono stati testati e approvati per l'utilizzo e quali computer sono aggiornati. Queste informazioni sono importanti per ridurre il rischio che i computer vengano compromessi e per rilevare gli utenti che hanno installato gli aggiornamenti non approvati.

  - **Informazioni sulla**     configurazione del sistema Questa categoria tiene traccia della funzione di un sistema, dell'interazione tra gli elementi del sistema e dei processi che dipendono da un sistema in esecuzione senza problemi. Ad esempio, il server proxy di terze parti può essere configurato in un server singolo. La dipendenza del server proxy su questo server dovrebbe essere compresa e i piani di emergenza potrebbero essere necessari se si verifica un errore. Se il server proxy può essere configurato per comunicare anche con un altro server front-end, è probabile che le dipendenze e i piani di contingenza vengano modificati.

<div>

## <a name="implementing-configuration-management"></a>Implementazione della gestione della configurazione

Dopo aver determinato gli elementi necessari per la gestione, implementare la gestione della configurazione tramite la raccolta dei dati e i dati di report. L'approccio più semplice per le organizzazioni di piccole dimensioni consiste nel raccogliere dati manualmente (numero e modello dei computer client, del sistema operativo, del software installato) e salvarlo in un documento di Office Word o Office Excel. Per i sistemi più grandi, più complessi e in continua evoluzione, è necessario automatizzare l'individuazione delle risorse e la raccolta di informazioni dettagliate. Decidere quali informazioni sono rilevanti per l'organizzazione e registrarle in un database.

Il database di gestione della configurazione è uno strumento utile per la gestione e il personale di supporto nelle aree seguenti:

  - **Controlli**     di sicurezza Il database consente di identificare i server che eseguono Lync Server e i sistemi di computer client che devono avere hotfix applicati o che hanno mancato l'installazione di un Service Pack o degli aggiornamenti antivirus più recenti.

  - **Installazione**     del software Identificare le versioni del software client e monitorarle consentirà agli amministratori di pianificare gli aggiornamenti delle versioni e le nuove installazioni, contribuendo anche alla documentazione relativa alle licenze e alla conformità.

  - **Informazioni sulla configurazione**     Se si gestisce un elenco aggiornato di tutte le impostazioni che sono state modificate rispetto all'impostazione predefinita, è possibile risolvere i problemi in modo rapido e più efficace.

  - **Pianificazione degli aggiornamenti**     Se una revisione della capacità rivela che è necessario ulteriore spazio di archiviazione sui server di database di Lync, è importante sapere se ogni server dispone di un controller RAID interno. Se lo fanno, allora sono lo stesso modello? Hanno lo stesso numero di dischi installati? Il database di gestione della configurazione indicherà il tipo di disco che può essere installato, il numero e il percorso di aggiornamento in ogni caso.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Strumenti utilizzati per la gestione della configurazione

Sono disponibili numerosi strumenti per individuare, controllare e segnalare le risorse. Alcuni di questi strumenti sono descritti in questa sezione.

  - **Script automatici**     È possibile scrivere script semplici per segnalare elementi quali il sistema operativo, il livello del Service Pack e se il software esiste su un insieme specifico di computer. È possibile scrivere questi script nei requisiti esatti di un'organizzazione. Tuttavia, il numero necessario di script e la relativa complessità può rendere gli script costosi per la creazione e la manutenzione.

  - **Strumenti automatici**     A seconda delle dimensioni dell'azienda e delle esigenze organizzative, è consigliabile utilizzare gli strumenti automatici. Strumenti quali Microsoft endpoint Configuration Manager incorporano modelli di report standard, ad esempio il livello di Service Pack, e consentono anche di creare report personalizzati, come in un'applicazione personalizzata. Microsoft endpoint Configuration Manager può essere utilizzato anche per il report sulle configurazioni hardware e software.

</div>

<div>

## <a name="relationship-with-change-management"></a>Relazione con la gestione delle modifiche

La gestione della configurazione è strettamente correlata alla gestione delle modifiche. La gestione della configurazione identifica la necessità di modificare e identifica e registra una modifica. Ad esempio, il database di gestione della configurazione può essere utilizzato per identificare i server che richiedono un hotfix. Change Management quindi definisce il processo per l'applicazione dell'hotfix.

Viceversa, se viene implementato un nuovo aggiornamento cumulativo, il processo di gestione delle modifiche dovrebbe fornire tali informazioni al sistema di gestione della configurazione. È probabile che gli strumenti di gestione della configurazione debbano essere configurati per identificare il nuovo software in modo che possano individuare e tenere presenti la posizione e la distribuzione del software.

</div>

</div>

<span> </span>

</div>

</div>

</div>

