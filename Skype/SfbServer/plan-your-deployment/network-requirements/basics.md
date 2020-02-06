---
title: Nozioni di base sul DNS
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
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 include un software incorporato in grado di fornirvi servizi DNS, quindi è consigliabile rivedere la documentazione disponibile, ad esempio la Guida allo scenario dei criteri DNS. Se si preferisce, è possibile scegliere una soluzione di terze parti.
ms.openlocfilehash: 5438ee6ccedda6e840ca706cf285af49326a3bf4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815794"
---
# <a name="dns-basics"></a>Nozioni di base sul DNS
 
Windows Server 2016 include un software incorporato in grado di fornirvi servizi DNS, quindi è consigliabile rivedere la documentazione disponibile, ad esempio la [Guida allo scenario dei criteri DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Se si preferisce, è possibile scegliere una soluzione di terze parti.
  
Ti consigliamo di usare una procedura consigliata per dedicare un server specifico all'implementazione per il DNS. Potresti configurarlo in uno dei server dedicati a uno dei ruoli di Skype for Business Server, ma se il server facesse parte di un pool e fossi stato smantellato per sbaglio, Skype for business si sarebbe guastato finché i servizi DNS non fossero stati ristabiliti.
  
## <a name="dns-records"></a>Record DNS

Ogni mapping di un nome a un indirizzo IP (che potrebbe essere un indirizzo IPv4 o IPv6) viene archiviato in un record DNS nel server DNS. Il nome è descritto nel report DNS in modo specifico come FQDN, un nome di dominio completo. Mentre *contoso.com* è un nome di dominio valido, è una scorciatoia per * \*. contoso.com* , quindi è ambiguo e potrebbe riferirsi a qualsiasi server nel dominio. Un esempio di FQDN che fa riferimento a un singolo server nel dominio può essere **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome host e non un nome di dominio completo (FQDN). Generatore di topologie USA FQDN e non i nomi host. Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio. Quando si assegnano FQDN ai server che usano Skype for Business Server, è necessario **usare solo caratteri standard** (inclusi a-z, a-z, 0-9 e segni meno). Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche, ovvero quando il nome di dominio completo deve essere assegnato a SN nel certificato.
  
Oltre a un indirizzo IP, il nome di dominio completo può essere mappato **a un indirizzo** IP virtuale. Un VIP è un indirizzo IP che non corrisponde a un'interfaccia di rete fisica effettiva. Un VIP spesso punta a un pool di server che eseguono un ruolo del server o a una coppia di server configurati per la ridondanza e la tolleranza d'errore.
  
Esistono diversi tipi di record DNS, quelli più rilevanti per la discussione: 
  
- **A** : un record di indirizzo o un record host restituisce un indirizzo IPv4 di 32 bit. Più comunemente usato per mappare gli hostname a un indirizzo IP dell'host.
    
- **Aaaa** : un record di indirizzi IPv6. Restituisce un indirizzo IPv6 di 128 bit. Più comunemente usato per mappare gli hostname a un indirizzo IP dell'host.
    
- **CNAME** : un record di nome canonico. In questo modo si risolve un nome in un altro: la ricerca DNS ritenterà la ricerca con il nuovo nome.
    
- **SRV** : un record di servizio (SRV record) specifica un servizio (processo in un server) a cui si accede in una specifica combinazione di porte e IP. I nomi dei servizi che richiedono un record di servizio sono corretti e non possono essere personalizzati oltre a renderli parte del dominio SIP. Alcuni servizi utente usano URL semplici. Un record SRV deve puntare a una posizione nello stesso dominio SIP, quindi se si hanno più domini è necessario più record SRV per un servizio specifico.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Come scegliere un nome di dominio SIP
<a name="BK_NameSIP"> </a>

Il nome di dominio SIP di un'organizzazione viene in genere allineato agli indirizzi di posta elettronica assegnati agli utenti. Se un utente dell'organizzazione ha un indirizzo di posta elettronica come Brown@contoso.com, il dominio \<\> SIP preferito per un'organizzazione con il nome di dominio contoso.com è semplicemente contoso.com.
  
### <a name="multiple-sip-domains"></a>Più domini SIP

 L'organizzazione potrebbe in alcuni casi avere bisogno di diversi domini SIP. Ad esempio, se Fabrikam.com è stato acquisito da contoso.com, potrebbe essere necessario creare un nuovo dominio SIP riconosciuto da Skype for Business Server e da cui si accetterà la connessione. Quando si esegue questa operazione, è necessario creare un set aggiuntivo di tutti i record DNS che usano contoso.com, con i nuovi FQDN che mostrano dove inviare le richieste per fabrikam.
  
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="BK_NameSIP"> </a>

È possibile usare il DNS per condividere il carico di traffico tra più server configurati come pool di server. A questo scopo, devi creare diversi record per il nome di dominio completo del pool, ognuno dei quali punta all'indirizzo IP di un nodo nel pool.
  
Vedere [bilanciamento del carico DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) per altre discussioni sul bilanciamento del carico.
  

