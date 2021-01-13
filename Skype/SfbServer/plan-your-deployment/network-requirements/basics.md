---
title: Informazioni di base sul DNS
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 dispone di software incorporato che può fornire servizi DNS, pertanto è possibile esaminare la documentazione disponibile, ad esempio la Guida allo scenario dei criteri DNS. Se si preferisce, è possibile scegliere una soluzione di terze parti.
ms.openlocfilehash: dc60bab84220cad306deee408a6a09fc16df5a10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825586"
---
# <a name="dns-basics"></a>Informazioni di base sul DNS
 
Windows Server 2016 dispone di software incorporato che può fornire servizi DNS, pertanto è possibile esaminare la documentazione disponibile, ad esempio la Guida allo [scenario dei criteri DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Se si preferisce, è possibile scegliere una soluzione di terze parti.
  
È consigliabile, come procedura consigliata, dedicare un server specifico all'implementazione per fornire il DNS. Potrebbe essere possibile configurarlo su uno dei server dedicati a uno dei ruoli del server Skype for business, ma se anche quel server facesse parte di un pool e venisse disattivata per errore, Skype for business potrebbe non funzionare correttamente fino a quando i servizi DNS non sono stati ristabiliti.
  
## <a name="dns-records"></a>Record DNS

Ogni mapping di un nome a un indirizzo IP (e potrebbe essere un indirizzo IPv4 o IPv6) è memorizzato in un record DNS sul server DNS. Il nome viene descritto nel report DNS in modo specifico come FQDN, ovvero un nome di dominio completo. Mentre *contoso.com* è un nome di dominio valido, è stenografia per *\* . contoso.com* , quindi è ambiguo e potrebbe riferirsi a qualsiasi server del dominio. Un esempio di FQDN che si riferisce a un singolo server nel dominio potrebbe essere **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Per impostazione predefinita, il nome del computer di un computer che non è aggiunto a un dominio è un nome host e non un nome di dominio completo (FQDN). Generatore di topologie utilizza FQDN, non nomi host. Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Quando si assegnano FQDN ai server che eseguono Skype for Business Server, è possibile **utilizzare solo caratteri standard** (tra cui a-z, a-z, 0-9 e segni meno). Non utilizzare caratteri Unicode o di sottolineatura. I caratteri non standard in un FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche (ovvero, quando il nome di dominio completo deve essere assegnato a SN nel certificato).
  
Oltre a un indirizzo IP, il nome di dominio completo può essere mappato **a un indirizzo** IP virtuale. Un VIP è un indirizzo IP che non corrisponde a un'interfaccia di rete fisica effettiva. Un VIP punta spesso a un pool di server che eseguono un ruolo del server o a una coppia di server configurati per la ridondanza e la tolleranza di errore.
  
Esistono diversi tipi di record DNS, quelli più rilevanti per la discussione: 
  
- **A** -un record di indirizzo o di host, restituisce un indirizzo IPv4 a 32 bit. Più comunemente utilizzato per mappare gli host a un indirizzo IP dell'host.
    
- **Aaaa** : record di indirizzi IPv6. Restituisce un indirizzo IPv6 a 128 bit. Più comunemente utilizzato per mappare gli host a un indirizzo IP dell'host.
    
- **CNAME** : record del nome canonico. Questo risolve un nome all'altro: la ricerca DNS ritenterà la ricerca con il nuovo nome.
    
- **SRV** -un record del servizio (SRV record) specifica un servizio (processo su un server) a cui si accede su una specifica combinazione di porte e IP. I nomi dei servizi che richiedono un record del servizio sono corretti e non possono essere personalizzati oltre a renderli parte del dominio SIP. Alcuni servizi utente utilizzano URL semplici. Un record SRV deve puntare a una posizione nello stesso dominio SIP, quindi se sono presenti più domini, è necessario disporre di più record SRV per un determinato servizio.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Come scegliere un nome di dominio SIP
<a name="BK_NameSIP"> </a>

Il nome di dominio SIP di un'organizzazione in genere è allineato agli indirizzi di posta elettronica assegnati ai propri utenti. Se un utente dell'organizzazione dispone di un indirizzo di posta elettronica come Brown@contoso.com, il \<sip-domain\> nome di dominio preferito per un'organizzazione con il contoso.com è semplicemente contoso.com.
  
### <a name="multiple-sip-domains"></a>Più domini SIP

 In alcuni casi, l'organizzazione potrebbe richiedere diversi domini SIP. Ad esempio, se Fabrikam.com è stato acquisito da contoso.com, potrebbe essere necessario creare un nuovo dominio SIP che Skype for Business Server riconosce e accetterà la connessione. Quando si esegue questa operazione, è necessario creare un ulteriore set di tutti i record DNS che utilizzano contoso.com, con i nuovi FQDN che mostrano dove inviare le richieste per fabrikam.
  
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="BK_NameSIP"> </a>

È possibile utilizzare DNS per condividere il carico del traffico tra diversi server configurati come pool di server. A tale scopo, è necessario creare più record a per il nome di dominio completo del pool, ognuno dei quali punta all'indirizzo IP di un nodo del pool.
  
Vedere [bilanciamento del carico DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) per ulteriori discussioni sul bilanciamento del carico.
  

