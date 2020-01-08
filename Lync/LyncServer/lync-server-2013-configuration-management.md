---
title: 'Lync Server 2013: Gestione configurazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa4bacdea1090351e9937e039fec184a1f59ab0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a>Gestione della configurazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-05-15_

La gestione della configurazione è il processo di registrazione e monitoraggio degli asset hardware e software e delle informazioni di configurazione del sistema. Viene in genere usato per tenere traccia delle licenze software, gestire una build hardware e software standard per i computer e i server client e definire gli standard di denominazione per i nuovi computer. La gestione della configurazione riguarda in genere le categorie seguenti:

  - **Hardware**   in questa categoria sono riportate le attrezzature di cui dispone l'organizzazione IT, dove si trovano le attrezzature e chi usa le attrezzature. Queste informazioni consentono a un'organizzazione di pianificare e preventivo per gli aggiornamenti, gestire le build hardware standard, segnalare il valore degli asset IT per scopi contabili e prevenire i furti.

  - **Software**   questa categoria consente di tenere traccia del software installato in ogni computer, i numeri di versione e la posizione delle licenze. Queste informazioni aiutano a pianificare gli aggiornamenti, a garantire che il software sia concesso in licenza e a rilevare la presenza di software non autorizzato (e senza licenza).

  - **Build standard questa**   categoria tiene traccia della build standard corrente per i computer e i server client e se i computer e i server client soddisfano questo standard. La definizione e l'applicazione di build standard aiuta il personale di supporto perché è necessario che il personale mantenga solo un numero limitato di versioni di ogni parte del software.

  - **Aggiornamenti cumulativi e hotfix**   questa categoria tiene traccia dei Service Pack che vengono testati e approvati per l'uso e quali sono i computer aggiornati. Queste informazioni sono importanti per ridurre il rischio che i computer vengano compromessi e per rilevare gli utenti che hanno installato aggiornamenti non approvati.

  - **Informazioni sulla configurazione del sistema**   questa categoria tiene traccia della funzione di un sistema, dell'interazione tra gli elementi di sistema e dei processi che dipendono da un sistema che viene eseguito senza problemi. Ad esempio, il server proxy di terze parti può essere configurato in un singolo server. La dipendenza del server proxy da questo server deve essere compresa e i piani di emergenza potrebbero essere necessari in caso di errore. Se il server proxy può essere configurato per comunicare anche con un altro server front-end, le dipendenze e i piani di emergenza cambieranno probabilmente.

<div>

## <a name="implementing-configuration-management"></a>Implementazione della gestione della configurazione

Dopo aver determinato gli elementi che devono essere gestiti, implementare la gestione della configurazione raccogliendo dati e segnalando i dati. L'approccio più semplice per le piccole organizzazioni consiste nel raccogliere dati manualmente (numero e modello di computer client, sistema operativo, software installato) e salvarlo in un documento di Office Word o Office Excel. Per sistemi più grandi, più complessi e in continuo cambiamento, la scoperta di asset e la raccolta di informazioni dettagliate deve essere automatizzata. Decidere quali informazioni sono rilevanti per l'organizzazione e registrarle in un database.

Il database di gestione della configurazione è uno strumento utile per supportare il personale e la gestione nelle aree seguenti:

  - **Verifiche di sicurezza**   il database consente di identificare i server che esegue Lync Server e i sistemi di computer client che devono avere gli hotfix applicati o che hanno perso l'installazione di un Service Pack o degli aggiornamenti più recenti degli antivirus.

  - **L'installazione**   del software che identifica le versioni del software client e il loro monitoraggio aiuteranno gli amministratori a pianificare gli aggiornamenti della versione e le nuove installazioni e anche aiutando la documentazione e la conformità delle licenze.

  - **Informazioni sulla**   configurazione se si mantiene un elenco aggiornato di tutte le impostazioni modificate rispetto all'impostazione predefinita, sarà possibile risolvere i problemi in modo rapido e più efficace.

  - **Pianificazione degli aggiornamenti**   se una revisione della capacità rivela che è necessario ulteriore spazio di archiviazione per i server di database Lync, è importante sapere se ogni server ha un controller RAID interno. Se lo fanno, allora lo stesso modello? Hanno lo stesso numero di dischi installati? Il database di gestione della configurazione indicherà il tipo di disco che può essere installato, il numero e il percorso di aggiornamento in ogni caso.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Strumenti usati per la gestione della configurazione

Esistono molti strumenti per individuare, controllare e segnalare asset. Alcuni di questi strumenti sono illustrati in questa sezione.

  - **Script automatizzati**   è possibile scrivere semplici script per segnalare elementi come il sistema operativo, il livello di Service Pack e se il software esiste in un set di computer specifico. Puoi scrivere questi script nei requisiti esatti di un'organizzazione. Tuttavia, il numero necessario di script e la loro complessità possono rendere gli script costosi da creare e gestire.

  - **Strumenti automatici a**   seconda delle dimensioni dell'azienda e delle esigenze dell'organizzazione, è consigliabile usare gli strumenti automatici. Gli strumenti, ad esempio System Center Configuration Manager, incorporano modelli di report standard (ad esempio il livello di Service Pack) e consentono anche di creare report personalizzati, ad es. per un'applicazione personalizzata. System Center Configuration Manager può essere usato anche per il report sulle configurazioni hardware e software.

</div>

<div>

## <a name="relationship-with-change-management"></a>Relazione con la gestione delle modifiche

La gestione della configurazione è strettamente correlata alla gestione delle modifiche. La gestione della configurazione identifica la necessità di modifiche e identifica e registra che si è verificata una modifica. Ad esempio, il database di gestione della configurazione può essere usato per identificare i server che richiedono un hotfix. La gestione delle modifiche definisce quindi il processo per l'applicazione dell'hotfix.

Viceversa, se viene implementato un nuovo aggiornamento cumulativo, il processo di gestione delle modifiche deve fornire queste informazioni al sistema di gestione della configurazione. Gli strumenti di gestione della configurazione dovranno probabilmente essere configurati per identificare il nuovo software in modo che possano individuare e individuare dove e quando viene distribuito il software.

</div>

</div>

<span> </span>

</div>

</div>

</div>

