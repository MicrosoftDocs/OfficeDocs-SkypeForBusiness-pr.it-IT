---
title: Requisiti DNS per gli URL semplici in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: "Riepilogo: esaminare le semplici considerazioni sull'URL in questo argomento prima di implementare i record DNS per Skype for Business Server."
ms.openlocfilehash: 7eb734fb4a9005f833f27efd3b0d180593155f39
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815784"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisiti DNS per gli URL semplici in Skype for Business Server

**Riepilogo:** Esaminare le semplici considerazioni sull'URL in questo argomento prima di implementare i record DNS per Skype for Business Server.

Gli URL semplici semplificano la partecipazione alle riunioni per gli utenti e rendono più semplice l'accesso agli strumenti di amministrazione di Skype for Business Server per gli amministratori. Gli URL semplici usano il proprio dominio, che non deve corrispondere ad alcuno dei domini SIP definiti. 

Skype for Business Server supporta i tre semplici URL seguenti: Meet, Dial-in e admin. È necessario configurare URL semplici per riunioni e accesso esterno e l'URL semplice per l'amministratore è facoltativo. I record DNS (Domain Name System) necessari per supportare gli URL semplici dipendono dal modo in cui sono stati definiti questi URL semplici e se si vuole supportare il ripristino di emergenza per gli URL semplici. 

## <a name="simple-url-scope"></a>Ambito URL semplice

Puoi configurare gli URL semplici per avere un ambito globale oppure puoi specificare URL semplici diversi per ogni sito centrale dell'organizzazione. Se sono specificati sia un URL semplice globale che un URL semplice del sito, l'URL semplice del sito ha la precedenza. 

Nella maggior parte dei casi è consigliabile impostare URL semplici solo a livello globale, in modo che l'URL di riunione semplice dell'utente non venga modificato se si passa da un sito a un altro. L'eccezione è costituita dalle organizzazioni che devono usare numeri di telefono diversi per gli utenti con accesso esterno in siti diversi. Tieni presente che se imposti un semplice URL (ad esempio l'URL semplice in accesso esterno) in un sito per essere un URL semplice a livello di sito, devi anche impostare gli altri URL semplici di tale sito come a livello di sito.

Puoi impostare URL semplici globali in Generatore di topologie. Per impostare un URL semplice a livello di sito, usare il cmdlet Set-CsSimpleURLConfiguration.

La definizione di un URL semplice richiederà anche l'impostazione di un record A e/o AAAA nella configurazione DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Regole di denominazione e convalida URL semplici
<a name="BK_Valid"> </a>

Generatore di topologie e i cmdlet di Skype for Business Server Management Shell applicano diverse regole di convalida per gli URL semplici. È necessario impostare URL semplici per le riunioni e la chiamata, ma l'impostazione di una per l'amministratore è facoltativa. Ogni dominio SIP deve avere un URL semplice Meet distinto, ma è necessario un solo URL semplice dialin e un URL semplice per l'amministratore per l'intera organizzazione.

Ogni URL semplice nell'organizzazione deve avere un nome univoco e non può essere un prefisso di un altro URL semplice (ad esempio, non è stato possibile impostare SfB2015.contoso.com/Meet come URL semplice di riunione e SfB2015.contoso.com/Meet/Dialin come URL semplice di accesso esterno). I nomi di URL semplici non possono contenere il nome di dominio completo di uno dei pool o qualsiasi informazione sulla https://FQDN:88/meet porta, ad esempio non è consentita. Tutti gli URL semplici devono iniziare con il prefisso https://. 

Gli URL semplici possono contenere solo caratteri alfanumerici, ovvero a-z, A-Z, 0-9 e il punto (.). Se si usano altri caratteri, gli URL semplici potrebbero non funzionare come previsto.

## <a name="changing-simple-urls-after-deployment"></a>Modifica di URL semplici dopo la distribuzione
<a name="BK_Valid"> </a>

Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere consapevoli del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici. Se la base di un URL semplice cambia, è necessario modificare anche i record DNS e i certificati. Ad esempio, passando da https://SfB2015.contoso.com/Meet per https://meet.contoso.com cambiare l'URL di base da SfB2015.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati per fare riferimento a meet.contoso.com. Se è stato modificato l'URL https://SfB2015.contoso.com/Meet semplice https://SfB2015.contoso.com/Meetings, l'url di base di SfB2015.contoso.com rimane invariato, quindi non sono necessarie modifiche DNS o di certificato.

Ogni volta che si modifica un nome di URL semplice, è necessario eseguire **Enable-CsComputer** su ogni Director e front end server per registrare la modifica.

## <a name="naming-examples-for-simple-urls"></a>Esempi di denominazione per URL semplici
<a name="BK_Valid"> </a>

Sono disponibili tre opzioni consigliate per la denominazione degli URL semplici. Quale opzione si sceglie ha implicazioni per configurare i record DNS e i certificati che supportano gli URL semplici. In ogni opzione è necessario configurare un URL semplice di riunione per ogni dominio SIP dell'organizzazione. 

È sempre necessario un solo URL semplice nell'intera organizzazione per l'accesso esterno e uno per l'amministratore, indipendentemente dal numero di domini SIP.

Nell'opzione 1 si crea un nuovo nome di dominio SIP per ogni URL semplice.

Se si usa questa opzione, è necessario un record DNS distinto per ogni URL semplice e ogni URL semplice Meet deve essere denominato nei certificati.

**Opzione di denominazione semplice URL 1**


| **URL semplice** <br/> | **Esempio** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Soddisfano  <br/>          | https://meet.contoso.com, https://meet.fabrikam.come così via (uno per ogni dominio SIP nell'organizzazione)  <br/> |
| Accesso esterno  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Admin  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Con l'opzione 2, gli URL semplici si basano sul nome di dominio SfB2015.contoso.com. Di conseguenza, è necessario un solo record DNS che consenta A tutti e tre i tipi di URL semplici. Questo record DNS fa riferimento A SfB2015.contoso.com. È inoltre necessario separare i record DNS per altri domini SIP nell'organizzazione. 

**Opzione di denominazione semplice URL 2**


| **URL semplice** <br/> | **Esempio** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Soddisfano  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meete così via (uno per ogni dominio SIP nell'organizzazione)  <br/> |
| Accesso esterno  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

L'opzione 3 è molto utile se si hanno molti domini SIP e si vuole che dispongano di URL semplici per riunioni separate, ma che si vogliano ridurre al minimo i requisiti di record e certificati DNS per questi URL semplici. 

**Opzione di denominazione URL semplice 3**


| **URL semplice** <br/> | **Esempio** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Soddisfano  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Accesso esterno  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opzione di ripristino di emergenza per URL semplici
<a name="BK_Valid"> </a>

Se si hanno più siti che contengono pool Front-end e il provider DNS supporta GeoDNS, è possibile configurare i record DNS per gli URL semplici per supportare il ripristino di emergenza, in modo che le funzionalità degli URL semplici continuino anche se si abbassa un intero pool Front-end. Questa funzionalità di ripristino di emergenza supporta gli URL semplici di riunione e accesso esterno.

Per configurare la configurazione, creare due indirizzi di GeoDNS. Ogni indirizzo contiene due record DNS A o CNAME che vengono risolti in due pool combinati per scopi di ripristino di emergenza. Un indirizzo GeoDNS viene usato per l'accesso interno e viene risolto nell'indirizzo IP di FQDN Web interno o di bilanciamento del carico per i due pool. L'altro indirizzo GeoDNS viene usato per l'accesso esterno e si risolve nell'FQDN Web esterno o nell'indirizzo IP del bilanciamento del carico per i due pool. Di seguito è riportato un esempio per l'URL semplice Meet, che usa i nomi di dominio completi per i pool. 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Crea quindi i record CNAME che risolvono l'URL semplice di riunione (ad esempio meet.contoso.com) ai due indirizzi di GeoDNS.

> [!NOTE]
> Se la rete usa hairpinning (instradando tutto il traffico di URL semplice tramite il collegamento esterno, incluso il traffico proveniente dall'interno dell'organizzazione), è possibile configurare l'indirizzo di GeoDNS esterno e risolvere l'URL semplice che si incontra solo in questo indirizzo esterno.

Quando usi questo metodo, puoi configurare ogni indirizzo di GeoDNS in modo da usare un metodo Round Robin per distribuire le richieste ai due pool oppure per connetterti principalmente a un pool, ad esempio il pool situato geograficamente più vicino, e usare l'altro pool solo in caso di errore di connettività. 

È possibile configurare la stessa configurazione per l'URL semplice con accesso esterno. A questo scopo, crea altri record come quelli nell'esempio precedente, sostituendo `dialin` per `meet` i record DNS. Per l'URL semplice amministratore, usa una delle tre opzioni elencate in precedenza in questa sezione.

Una volta configurata questa configurazione, è necessario usare un'applicazione di monitoraggio per configurare il monitoraggio HTTP per la visualizzazione degli errori. Per l'accesso esterno, monitorare per verificare che HTTPS OTTENGa lyncdiscover.<sipdomain> le richieste per l'FQDN Web esterno o per l'indirizzo IP del bilanciamento del carico per i due pool hanno esito positivo. Ad esempio, le richieste seguenti non devono contenere alcuna intestazione **Accept** e devono restituire **200 OK**.

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Per l'accesso interno, è necessario monitorare la porta 5061 nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. Se vengono rilevati errori di connettività, il VIP per questi pool deve chiudere le porte 80, 443 e 4443.


