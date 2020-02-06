---
title: Installazione di software facoltativo in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 usando lo strumento di pianificazione di Skype for Business Server 2015, è necessario prima di tutto installare lo strumento di pianificazione. Lo strumento di pianificazione non deve essere distribuito in una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'uso dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono duplicate qui per chiarezza.
ms.openlocfilehash: 29cadae219faadb68a8a027de11309efc8e3f10b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816385"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a>Installazione di software facoltativo in Lync Server 2013

Prima di iniziare a progettare e pianificare l'infrastruttura di Skype for Business Server 2015 usando lo strumento di pianificazione di Skype for Business Server 2015, è necessario prima di tutto installare lo strumento di pianificazione. Lo strumento di pianificazione non deve essere distribuito in una workstation o un server che fa parte del dominio o dell'infrastruttura in cui si prevede di installare Skype for Business Server 2015. Il file Readme che accompagna lo strumento di pianificazione descrive in dettaglio informazioni importanti sull'installazione e l'uso dello strumento. Alcune delle informazioni contenute nel file Leggimi vengono duplicate qui per chiarezza.

> [!IMPORTANT]
> Lo strumento di pianificazione richiede l'installazione da parte di un utente con diritti e autorizzazioni di amministratore nel computer in cui deve essere installato lo strumento.

I sistemi operativi supportati per l'installazione e il funzionamento dello strumento di pianificazione sono i seguenti:

- Windows 10

- Windows 8

- Windows 8.1

- Windows Server 2012

- Windows Server 2012 R2

- Windows 7, 32 bit Edition

- Windows 7, 64 bit Edition con Windows su Win32 (WOW)

- Windows Server 2008 R2 con WOW

Inoltre, lo strumento di pianificazione richiede Microsoft .NET Framework 4,5.

Dopo aver soddisfatto i requisiti di preinstallazione, è possibile installare lo strumento di pianificazione.



## <a name="to-install-the-planning-tool"></a>Per installare lo strumento di pianificazione

1. Accedere al computer locale come membro del gruppo Administrators.

2. Usando Esplora risorse o una finestra di comando, individuare la directory in cui sono stati scaricati i file di installazione dello strumento di pianificazione.

3. Individuare il file SkypeForBusinessPlanningTool. msi. In Esplora risorse fare doppio clic sul file. Nella finestra di comando digitare il nome del file e quindi premere **invio** per eseguire il file.

4. Nella pagina iniziale di **Skype for Business Server 2015, configurazione guidata strumento di pianificazione**, fare clic su **Avanti**.

5. Esaminare il **contratto di licenza con l'utente finale**, selezionare **Accetto i termini del contratto di licenza** se si sceglie di accettare le condizioni per l'uso nel contratto di licenza e quindi fare clic su **Avanti**.

6. Scegliere la posizione in cui installare i file dello strumento di pianificazione. Il percorso predefinito è C:\Programmi (x86) \Skype for Business Server 2015 \ Planning Tool. Se si vuole modificare il percorso di installazione, fare clic su **Cambia**. In **modifica cartella di destinazione**selezionare o digitare la posizione in cui installare i file, fare clic su **OK**e quindi su **Avanti**.

7. Il programma di installazione è ora pronto per l'installazione dello strumento di pianificazione. Fare clic su **Installa** per avviare il processo di installazione.

8. L'installazione verrà avviata e verrà visualizzato lo stato di avanzamento. Dopo aver completato l'installazione, fare clic su **fine**.

9. Lo strumento di pianificazione è pronto per l'uso.

## <a name="optional-software"></a>Software facoltativo
<a name="Optional_Software"> </a>

Lo strumento di pianificazione di Skype for Business Server 2015 è progettato per l'esportazione in Microsoft Excel e Microsoft Visio. Anche se queste applicazioni non sono necessarie per il funzionamento dello strumento di pianificazione, aggiungono un valore significativo alla distribuzione e alla documentazione del progetto.

### <a name="microsoft-excel"></a>Microsoft Excel

L'esportazione della progettazione in Microsoft Excel consente di creare un report che visualizza sette schede nel foglio di calcolo:

- Riepilogo: Visualizza le informazioni sulla configurazione del sito, inclusi il conteggio degli utenti, le impostazioni della capacità e le informazioni sul profilo del server.

- Profilo hardware: Visualizza un report sulle configurazioni hardware consigliate per i server specificati nella topologia, tra cui CPU, memoria, disco e interfaccia di rete. Sono incluse anche la quantità e le specifiche consigliate per i componenti server. Ogni server viene inoltre definito dal sito per ottenere una rappresentazione completa dei requisiti del server per sito.

- Requisiti per le porte: Visualizza un report di tutte le porte abilitate e l'associazione a Domain Name System Load Balancing (DNS LB) e hardware load balancers (HLB). È consigliabile usare questo report per pianificare le configurazioni firewall e DNS LB e HLB.

- Report di riepilogo: Visualizza il riepilogo generale delle impostazioni necessarie per configurare la rete Edge Server.

- Report certificati: Visualizza il nome dell'oggetto e i nomi alternativi oggetto necessari per i certificati necessari per l'uso dei server perimetrali.

- Report firewall: Visualizza le porte di origine e di destinazione e gli indirizzi IP per le interfacce esterne ed interne.

- Report DNS: Visualizza il nome di dominio completo (FQDN) e gli indirizzi IP/VIP necessari per ogni voce DNS creata.

### <a name="microsoft-visio"></a>Microsoft Visio

L'esportazione della progettazione in Microsoft Visio crea un diagramma da usare per la documentazione della topologia e dell'infrastruttura configurate. Il diagramma importato può essere modificato e ridisposto per soddisfare le esigenze della documentazione. Il diagramma di Visio tipico includerà:

> [!NOTE]
> Se la struttura è abbastanza grande da richiedere più di tre server front-end, verrà creata una pagina aggiuntiva per il pool Front-End, i server front-end, il computer in cui sono in esecuzione SQL Server, gli indirizzi IP e i nomi di dominio completi.

- Topologia globale-diagramma dei siti di Skype for Business Server 2015 configurati.

- Scheda nome sito: Visualizza la topologia di configurazione del sito con Edge Server, firewall, PSTN (Public Switched Telephone Network) con gateway e la distribuzione del server interno. La distribuzione interna è costituita da server e pool configurati, inclusi i pool Front-End, i server basati su SQL Server, i servizi di dominio Active Directory, i direttori, i server di messaggistica unificata di Exchange, i server cassette postali di Exchange, i server di Office Web Apps Mediation Server e server di chat permanenti.

- Diagramma reticolare Edge-diagramma che descrive la configurazione del server perimetrale con gli indirizzi IP associati e i nomi di dominio completi. Sono inclusi anche il bilanciamento del carico DNS e i dispositivi di bilanciamento del carico hardware. Vengono inoltre visualizzati i direttori e il server front-end o il pool Front-End, con il DNS LB o HLB associato e l'indirizzo IP assegnato (lo strumento di pianificazione supporta sia gli indirizzi IPv4 che IPv6) e il nome di dominio completo.

## <a name="see-also"></a>Vedere anche
<a name="Optional_Software"> </a>

[Installazione dello strumento di pianificazione](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
