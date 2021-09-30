---
title: Requisiti DNS per gli URL semplici in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: "Riepilogo: leggere le considerazioni relative all'URL semplice in questo argomento prima di implementare i record DNS per Skype for Business Server."
ms.openlocfilehash: cbc8a6f99704f9c450847d0ca3c5173b0066715e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011720"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisiti DNS per gli URL semplici in Skype for Business Server

**Riepilogo:** Leggere le considerazioni relative all'URL semplice in questo argomento prima di implementare i record DNS per Skype for Business Server.

Gli URL semplici semplificano la partecipazione alle riunioni per gli utenti e semplificano l'accesso Skype for Business Server agli amministratori. Gli URL semplici utilizzano il proprio dominio, che non deve corrispondere ad alcun dominio SIP definito. 

Skype for Business Server supporta i tre URL semplici seguenti: Meet, Dial-In e Admin. È necessario configurare URL semplici per Meet e Accesso esterno e l'URL semplice amministratore è facoltativo. I record DNS (Domain Name System) necessari per supportare gli URL semplici dipendono da come sono stati definiti gli URL e dall'eventuale impostazione del supporto del ripristino di emergenza per gli URL semplici. 

## <a name="simple-url-scope"></a>Ambito URL semplice

È possibile configurare gli URL semplici per un ambito globale oppure specificare URL semplici diversi per ogni sito centrale dell'organizzazione. Se vengono specificati sia un URL semplice globale che un URL semplice di sito, quest'ultimo avrà la priorità. 

Nella maggior parte dei casi, è consigliabile impostare url semplici solo a livello globale, in modo che l'URL semplice Meet di un utente non cambi se si sposta da un sito a un altro. L'eccezione è rappresentata da organizzazioni che devono utilizzare numeri di telefono diversi per gli utenti connessi tramite chiamata in ingresso in siti diversi. Si noti che se si imposta in un sito un URL semplice a livello di sito, ad esempio per l'accesso esterno, sarà necessario impostare a livello di sito anche gli altri URL semplici del sito.

È possibile impostare URL semplici globali in Generatore di topologie. Per impostare un URL semplice a livello di sito, utilizzare il cmdlet Set-CsSimpleURLConfiguration.

La definizione di un URL semplice richiederà anche l'impostazione di un record A e/o AAAA nella configurazione DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Regole di denominazione e convalida degli URL semplici
<a name="BK_Valid"> </a>

Generatore di topologie e i cmdlet Skype for Business Server Management Shell applicano diverse regole di convalida per gli URL semplici. È obbligatorio impostare URL semplici riunione e per accesso esterno, mentre l'impostazione dell'URL semplice di amministrazione è facoltativa. Ogni dominio SIP deve disporre di un URL semplice riunione separato, ma sono sufficienti un URL semplice per accesso esterno e un URL semplice di amministrazione per l'intera organizzazione.

Ogni URL semplice dell'organizzazione deve avere un nome univoco e non può essere un prefisso di un altro URL semplice( ad esempio, non è possibile impostarlo come URL semplice Meet e come URL semplice `SfB2015.contoso.com/Meet` `SfB2015.contoso.com/Meet/Dialin` dialin). I nomi di URL semplici non possono contenere il nome di dominio completo di alcun pool o le informazioni sulle porte (ad esempio, https://FQDN:88/meet non sono consentite). Tutti gli URL semplici devono iniziare con il prefisso https:// semplice. 

Gli URL semplici possono includere solo caratteri alfanumerici, ovvero a-z, A-Z, 0-9 e il punto (.). Se si utilizzano altri caratteri, gli URL semplici potrebbero non funzionare come previsto.

## <a name="changing-simple-urls-after-deployment"></a>Modifica degli URL semplici dopo la distribuzione
<a name="BK_Valid"> </a>

Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario tenere presente l'impatto della modifica sui record DNS e sui certificati per gli URL semplici. Se la base di un URL semplice cambia, è necessario modificare anche i record DNS e i certificati. Ad esempio, se si cambia l'URL di base da a , è necessario modificare i record DNS e i certificati in modo che `https://SfB2015.contoso.com/Meet` `https://meet.contoso.com` `SfB2015.contoso.com` `meet.contoso.com` facciano riferimento a `meet.contoso.com` . Se è stato modificato l'URL semplice da a , l'URL di base di rimane lo stesso, quindi non sono necessarie modifiche al `https://SfB2015.contoso.com/Meet` `https://SfB2015.contoso.com/Meetings` DNS o al `SfB2015.contoso.com` certificato.

Ogni volta che si modifica un nome URL semplice, tuttavia, è necessario eseguire **Enable-CsComputer** in ogni Server Director e Front End Server per registrare la modifica.

## <a name="naming-examples-for-simple-urls"></a>Esempi di denominazione per URL semplici
<a name="BK_Valid"> </a>

Sono disponibili tre opzioni consigliate per denominare gli URL semplici. L'opzione scelta determina il modo in cui vengono configurati i certificati e i record A DNS che supportano gli URL semplici. In ogni opzione è necessario configurare un URL semplice riunione per ogni dominio SIP dell'organizzazione. 

Sono sufficienti sempre nell'intera organizzazione un solo URL semplice per accesso esterno e uno di amministrazione, indipendentemente dal numero di domini SIP presenti.

Nell'opzione 1 viene creato un nuovo nome di dominio SIP per ogni URL semplice.

Se si utilizza questa opzione, è necessario un record A DNS separato per ogni URL semplice e ogni URL semplice riunione deve essere denominato nei certificati.

**Opzione 1 di denominazione degli URL semplici**


| **URL semplice** <br/> | **Esempio** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://meet.contoso.com`, `https://meet.fabrikam.com` e così via (uno per ogni dominio SIP dell'organizzazione)  <br/> |
| Accesso remoto  <br/>       | `<https://dialin.contoso.com>`  <br/>                                                                                  |
| Amministratore  <br/>         | `<https://admin.contoso.com>`  <br/>                                                                                   |

Con l'opzione 2, gli URL semplici si basano sul nome di dominio `SfB2015.contoso.com` . È necessario pertanto un solo record A DNS che consenta tutti e tre i tipi di URL semplici. Questo record DNS A fa riferimento `SfB2015.contoso.com` a . Sono sempre necessari però record A DNS separati per altri domini SIP dell'organizzazione. 

**Opzione 2 di denominazione degli URL semplici**


| **URL semplice** <br/> | **Esempio** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://SfB2015.contoso.com/Meet`, `https://SfB2015.fabrikam.com/Meet` e così via (uno per ogni dominio SIP dell'organizzazione)  <br/> |
| Accesso remoto  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                                          |
| Amministratore  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                                           |

L'opzione 3 è più utile se si dispone di numerosi domini SIP e si desidera che dispongano di URL semplici riunione separati, riducendo però al minimo i requisiti dei certificati e dei record DNS per questi URL semplici. 

**Opzione 3 di denominazione degli URL semplici**


| **URL semplice** <br/> | **Esempio** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `<https://SfB2015.contoso.com/contosoSIPdomain/Meet>`  <br/> `<https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>`  <br/> |
| Accesso remoto  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                            |
| Amministratore  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opzione di ripristino di emergenza per GLI URL semplici
<a name="BK_Valid"> </a>

Se si dispone di più siti che contengono pool Front End e il provider DNS supporta GeoDNS, è possibile configurare i record DNS per gli URL semplici in modo da supportare il ripristino di emergenza, in modo che la funzionalità URL semplice continui anche se un intero pool Front End si è arrestato. Questa funzionalità di ripristino di emergenza supporta gli URL semplici meet e dial-in.

Per eseguire questa configurazione, creare due indirizzi GeoDNS. Ogni indirizzo presenta due record DNS A o CNAME che si risolvono in due pool che vengono accoppiati per il ripristino di emergenza. Un indirizzo GeoDNS viene usato per l'accesso interno e si risolve nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. L'altro indirizzo GeoDNS viene usato per l'accesso esterno e si risolve nell'FQDN Web esterno o nell'indirizzo IP del bilanciamento del carico per i due pool. Di seguito viene riportato un esempio dell'URL semplice Riunione, in cui vengono usati gli FQDN per i pool. 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Crea quindi record CNAME che risolvono l'URL semplice Meet (ad esempio `meet.contoso.com` ) nei due indirizzi GeoDNS.

> [!NOTE]
> Se la rete usa l'hairpin (ovvero il routing di tutto il traffico degli URL semplici attraverso il collegamento esterno, incluso il traffico proveniente dall'organizzazione), è sufficiente configurare l'indirizzo GeoDNS esterno e risolvere l'URL semplice riunione solo nell'indirizzo esterno specifico.

Quando si usa questo metodo, è possibile configurare ciascun indirizzo GeoDNS in modo che usi un metodo round robin per distribuire le richieste nei due pool oppure per effettuare la connessione principalmente a un pool (ad esempio il pool geograficamente più vicino) e usare l'altro pool solo in caso di errore di connettività. 

È possibile specificare la stessa configurazione per l'URL semplice per accesso esterno. A tale scopo, creare record aggiuntivi come quelli dell'esempio precedente,  `dialin` `meet` sostituendoli nei record DNS. Per l'URL semplice di amministrazione, usare una delle tre opzioni elencate precedentemente in questa sezione.

Dopo avere completato la configurazione, è necessario usare un'applicazione di monitoraggio per impostare il monitoraggio HTTP per il controllo degli errori. Per l'accesso esterno, monitorare per assicurarsi che HTTPS GET lyncdiscover.<sipdomain> le richieste all'FQDN Web esterno o all'indirizzo IP del servizio di bilanciamento del carico per i due pool hanno esito positivo. Ad esempio, le richieste seguenti non devono includere alcuna intestazione **ACCEPT** e devono restituire **200 OK**.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Per l'accesso interno, è necessario monitorare la porta 5061 nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. Se vengono rilevati errori di connettività, il VIP per questi pool deve chiudere le porte 80, 443 e 4443.


