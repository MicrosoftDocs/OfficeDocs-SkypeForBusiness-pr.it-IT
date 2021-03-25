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
description: Windows Server 2016 dispone di software incorporato in grado di fornire servizi DNS, pertanto è possibile consultare la documentazione disponibile, ad esempio la Guida allo scenario dei criteri DNS. Se si preferisce, è possibile scegliere una soluzione di terze parti.
ms.openlocfilehash: 2e8655cb53228fbfe23bc62aaebbdfd5a02ce4f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116034"
---
# <a name="dns-basics"></a>Informazioni di base sul DNS
 
Windows Server 2016 dispone di software incorporato in grado di fornire servizi DNS, pertanto è possibile consultare la documentazione disponibile, ad esempio la Guida allo scenario dei criteri [DNS.](/windows-server/networking/dns/deploy/dns-policy-scenario-guide) Se si preferisce, è possibile scegliere una soluzione di terze parti.
  
Come procedura consigliata, è consigliabile dedicare un server specifico nell'implementazione per fornire DNS. Si potrebbe potenzialmente configurarlo in uno dei server dedicati a uno dei ruoli del server Skype for Business, ma se il server fosse anche parte di un pool e fosse stato disattivato per errore, Skype for Business non funzionarebbe fino a quando i servizi DNS non vengono nuovamente stabiliti.
  
## <a name="dns-records"></a>Record DNS

Ogni mapping di un nome a un indirizzo IP (e che potrebbe essere un indirizzo IPv4 o IPv6) viene archiviato in un record DNS sul server DNS. Il nome è descritto nel rapporto DNS in modo specifico come FQDN, ovvero un nome di dominio completo. Anche *contoso.com* è un nome di dominio valido, è abbreviazione di *\* .contoso.com,* quindi è ambiguo e potrebbe fare riferimento a qualsiasi server nel dominio. Un esempio di fqdn che fa riferimento a un singolo server nel dominio potrebbe **essere meeting01.contoso.com**.
  
> [!IMPORTANT]
> Per impostazione predefinita, il nome computer di un computer che non fa parte di un dominio è un nome host e non un nome di dominio completo (FQDN). In Generatore di topologie vengono utilizzati fqdn e non nomi host. Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non fa parte di un dominio. **Utilizzare solo caratteri standard** (inclusi A-Z, a-z, 0-9 e trattini) quando si assegnano FQDN ai server che eseguono Skype for Business Server. Non utilizzare caratteri Unicode o di sottolineatura. I caratteri non standard in un nome di dominio completo spesso non sono supportati da AUTORITÀ di certificazione pubbliche e DNS esterne, ovvero quando il nome di dominio completo deve essere assegnato al nome di dominio completo nel certificato.
  
Oltre a un indirizzo IP, il nome di dominio completo può essere mappato a un **VIP,** ovvero un indirizzo IP virtuale. Un VIP è un indirizzo IP che non corrisponde a un'interfaccia di rete fisica effettiva. Un VIP spesso punta a un pool di server che eseguono un ruolo del server o a una coppia di server configurati per la ridondanza e la tolleranza di errore.
  
Esistono diversi tipi di record DNS, quelli più rilevanti per questa discussione sono: 
  
- **A:** un record address o un record Host, restituisce un indirizzo IPv4 a 32 bit. Più comunemente usato per mappare i nomi host a un indirizzo IP dell'host.
    
- **AAAA ,** un record di indirizzo IPv6. Restituisce un indirizzo IPv6 a 128 bit. Più comunemente usato per mappare i nomi host a un indirizzo IP dell'host.
    
- **CNAME** : record di nome canonico. In questo modo viene risolto un nome in un altro: la ricerca DNS ritenterà la ricerca con il nuovo nome.
    
- **SRV** : un record di servizio (record SRV) specifica un servizio (un processo su un server) a cui si accede su una specifica combinazione di porta e IP. I nomi dei servizi che richiedono un record di servizio sono fissi e non possono essere personalizzati oltre a renderli parte del dominio SIP. Alcuni servizi utente usano URL semplici. Un record SRV deve puntare a una posizione nello stesso dominio SIP, quindi se si dispone di più domini sono necessari più record SRV per un determinato servizio.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Come scegliere un nome di dominio SIP
<a name="BK_NameSIP"> </a>

Il nome di dominio SIP di un'organizzazione in genere è allineato agli indirizzi di posta elettronica dati agli utenti. Se un utente dell'organizzazione dispone di un indirizzo di posta elettronica come Brown@contoso.com, il preferito per un'organizzazione con il nome di dominio contoso.com è semplicemente \<sip-domain\> contoso.com.
  
### <a name="multiple-sip-domains"></a>Più domini SIP

 L'organizzazione potrebbe in alcuni casi richiedere diversi domini SIP. Ad esempio, se Fabrikam.com è stato acquisito da contoso.com, potrebbe essere necessario creare un nuovo dominio SIP riconosciuto e accettato da Skype for Business Server. In questo caso, è necessario creare un set aggiuntivo di tutti i record DNS che utilizzano contoso.com, con nuovi FQDN che mostrano dove inviare le richieste per Fabrikam.
  
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="BK_NameSIP"> </a>

È possibile utilizzare DNS per condividere il carico di traffico tra diversi server impostati come pool di server. A tale scopo, è necessario creare diversi record A per il nome di dominio completo del pool, ognuno dei quali punta all'indirizzo IP di un nodo nel pool.
  
Per [ulteriori discussioni sul bilanciamento](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) del carico, vedere Bilanciamento del carico DNS.
