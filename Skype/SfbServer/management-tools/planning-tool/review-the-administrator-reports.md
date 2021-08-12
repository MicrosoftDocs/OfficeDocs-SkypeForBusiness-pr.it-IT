---
title: Esaminare i report dell'amministratore in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Nei rapporti di amministrazione sono incluse informazioni dettagliate per la distribuzione e le operazioni. I report vengono generati in base alle selezioni contrassegnate in Siti di progettazione. Il progettista può dare valore aggiunto ai rapporti modificando i diagrammi di rete e definendo gli indirizzi IP completi e i nomi di dominio completi (FQDN) dei server, dei pool e dei servizi di bilanciamento del carico.
ms.openlocfilehash: c74237f5d92d54a1a421ede7707565bba59582141e00d1a944a88c2e8c096c88
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54293973"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Esaminare i report dell'amministratore in Skype for Business Server 2015

Nei rapporti di amministrazione sono incluse informazioni dettagliate per la distribuzione e le operazioni. I report vengono generati in base alle selezioni contrassegnate in **Siti di progettazione.** Il progettista può dare valore aggiunto ai rapporti modificando i diagrammi di rete e definendo gli indirizzi IP completi e i nomi di dominio completi (FQDN) dei server, dei pool e dei servizi di bilanciamento del carico.

La funzionalità report amministratore consente di:

- [Esaminare il rapporto riepilogativo](review-the-administrator-reports.md#Summary_report)

- [Esaminare il report certificati](review-the-administrator-reports.md#Certificates_Report)

- [Esaminare il rapporto firewall](review-the-administrator-reports.md#Firewall_report)

- [Esaminare il rapporto DNS](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Esaminare il rapporto riepilogativo
<a name="Summary_report"> </a>

Il Skype for Business amministratore è il primo di quattro report importanti che documenta la progettazione in dettaglio. Le informazioni contenute in questo report e gli altri tre report associati sono utili per l'information technology Teams:

![Rapporto di amministrazione riepilogativo generale](../../media/General_Summary_Report_Admin_Report.png)

Nel rapporto riepilogativo vengono elencate informazioni di configurazione generali associate alla rete perimetrale. Vengono documentati il percorso, il nome di dominio completo (FQDN) e l'indirizzo IP, il tipo di rete e i commenti specifici di un determinato ruolo.

Il progettista e tutti i team che distribuiranno, gestiranno e gestiranno l'infrastruttura devono esaminare il rapporto riepilogativo per l'accuratezza e assicurarsi che gli errori siano almeno.

È inoltre possibile visualizzare report più dettagliati:

- Rapporto certificati

- Rapporto firewall

- Rapporto DNS

## <a name="review-the-certificates-report"></a>Esaminare il report certificati
<a name="Certificates_Report"> </a>

Il Report certificati contiene tutti i certificati necessari nella distribuzione consigliata Skype for Business Server 2015. Lo strumento di pianificazione consente di account per i nomi soggetto e i nomi alternativi soggetto immessi. Il testo predefinito non modificabile può rappresentare una potenziale sfida per il team responsabile della richiesta e dell'emissione dei certificati. Nelle informazioni sui certificati sono inoltre incluse informazioni sull'origine da cui in genere viene emesso il certificato. Se l'infrastruttura non dispone di un'infrastruttura a chiave pubblica (PKI), tutti i certificati possono essere richiesti tramite un provider di certificati pubblico. I campi relativi agli utilizzi chiave avanzati e alla destinazione del rapporto sono molto utili per comprendere lo scopo e il percorso di ogni certificato.

![Report amministratore certificati](../../media/Certificates_Report_Admin_Report.png)

Esaminare attentamente e assicurarsi di comprendere l'uso e lo scopo di ogni certificato nella distribuzione. Se c'è una domanda sull'utilizzo di un certificato, determinare quale server o servizio sta parlando con cosa. I certificati Skype for Business Server 2015 vengono utilizzati per due scopi principali:

- Mutual Transport Layer Security (MTLS) - I computer coinvolti nella comunicazione presentano ognuno un certificato che dimostra la propria identità a un altro computer. Questa operazione è nota come autenticazione server. La comunicazione non può iniziare finché ogni computer non considera attendibile l'identità dell'altro computer.

- Crittografia - La crittografia (Secure Sockets Layer, SSL e Transport Layer Security o TLS) è uno strumento fondamentale per proteggere le comunicazioni, garantire la privacy e creare un sistema di comunicazione e collaborazione attendibile.

## <a name="review-the-firewall-report"></a>Esaminare il rapporto firewall
<a name="Firewall_report"> </a>

Skype for Business Server 2015 ha un insieme potenzialmente complesso di regole firewall. Lo strumento di pianificazione riduce questa complessità generando un report che definisce in dettaglio tutti i requisiti del firewall, in base ai criteri di input del progettista. L'amministratore del firewall IT sarà in grado di utilizzare tale rapporto per configurare e definire le regole necessarie.

Dal punto di vista della gestione del firewall, il report deve essere esaminato attentamente per assicurarsi che non vi siano conflitti con l'uscita dalle regole del firewall e che non vi siano criteri o procedure che potrebbero essere violati.

![Report amministratore firewall](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Esaminare il rapporto DNS
<a name="DNS_Report"> </a>

Il rapporto DNS, che fa parte del rapporto dell'amministratore, dettaglia tutte le voci consigliate e note per dns (Domain Name System) nelle reti interne, perimetrali ed esterne. Se il progettista ha completato le modifiche al diagramma di rete e tutti gli indirizzi IP e i nomi di dominio completi (FQDN) sono definiti in base ai relativi valori di produzione, il rapporto DNS fornisce una risorsa di configurazione eccellente. Questo report può anche fungere da documento operativo per la risoluzione dei problemi.

![Rapporto amministratore DNS](../../media/DNS_Report_Admin_Report.png)

È consigliabile fare in modo che il team di gestione DNS riveda accuratamente il rapporto DNS per assicurarsi che non vi siano errori che potrebbero causare difficoltà durante la distribuzione o che potrebbero complicare una sessione di risoluzione dei problemi.

## <a name="see-also"></a>Vedere anche
<a name="DNS_Report"> </a>

[Esame dei rapporti di amministrazione](/previous-versions/office/lync-server-2013/lync-server-2013-reviewing-the-administrator-reports)