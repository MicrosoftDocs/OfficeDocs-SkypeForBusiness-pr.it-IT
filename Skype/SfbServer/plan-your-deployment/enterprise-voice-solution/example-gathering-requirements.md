---
title: Esempio di requisiti di raccolta per il controllo di ammissione di chiamata in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Fornisce un esempio dettagliato di pianificazione per il controllo dell'ammissione alle chiamate in Skype for Business Server VoIP aziendale, inclusa la raccolta di informazioni sui siti, le aree geografiche e la larghezza di banda della rete.
ms.openlocfilehash: 73a1a75f8619877d2c9228f910aa747aee36a8e0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187697"
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>Esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Skype for Business Server

Fornisce un esempio dettagliato di pianificazione per il controllo dell'ammissione alle chiamate in Skype for Business Server VoIP aziendale, inclusa la raccolta di informazioni sui siti, le aree geografiche e la larghezza di banda della rete.

Questo esempio illustra come pianificare e implementare il controllo di ammissione di chiamata (CAC). Ad alto livello, è costituito dalle attività seguenti:

1. Identificare tutti gli hub di rete e le dorsali (note come aree di rete).

2. Identificare il sito centrale di Skype for Business Server che gestirà CAC per ogni area di rete.

3. Identificare e definire i siti di rete connessi a ogni area di rete.

4. Per ogni sito di rete la cui connessione alla WAN è vincolata da larghezza di banda, descriva la capacità di larghezza di banda della connessione WAN e i limiti di larghezza di banda che l'amministratore di rete ha impostato per il traffico multimediale Skype for Business Server, se applicabile. Non è necessario includere siti la cui connessione alla rete WAN non è vincolata da larghezza di banda.

5. Associare ogni subnet della rete a un sito di rete.

6. Mappare i collegamenti tra le aree di rete. Per ogni collegamento, Descrivi la sua capacità di larghezza di banda e i limiti che l'amministratore di rete ha inserito nel traffico multimediale Skype for Business Server.

7. Definire una route tra ogni coppia di aree di rete.

## <a name="gather-the-required-information"></a>Raccogliere le informazioni necessarie

Per preparare il controllo di ammissione alle chiamate, raccogliere le informazioni descritte nei passaggi seguenti:

1. Identificare le aree di rete. Un'area di rete rappresenta un backbone di rete o un hub di rete. 

    Un backbone di rete o un hub di rete fa parte dell'infrastruttura di rete di computer che interconnette vari elementi di rete, fornendo un percorso per lo scambio di informazioni tra LAN o subnet diverse. Una backbone può legare insieme diverse reti, da una piccola posizione a un'area geografica ampia. La capacità della colonna vertebrale è in genere maggiore rispetto a quella delle reti connesse.

    La topologia di esempio include tre aree di rete: Nord America, EMEA e APAC. Un'area di rete contiene una raccolta di siti di rete. Collaborare con l'amministratore di rete per definire le aree di rete per l'organizzazione.

2. Identificare il sito centrale associato di ogni area di rete. Un sito centrale contiene almeno un server front-end ed è la distribuzione di Skype for Business Server che gestirà CAC per tutto il traffico multimediale che passa attraverso la connessione WAN dell'area di rete.

   **Esempio di rete aziendale divisa in tre aree di rete**

     ![Esempio di topologia di rete con tre aree di rete](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > Una rete MPLS (Multiprotocol Label Switching) deve essere rappresentata come area di rete in cui ogni posizione geografica contiene un sito di rete corrispondente. Per informazioni dettagliate, vedere [componenti e topologie per il controllo dell'ammissione alle chiamate in Skype for business](components-and-topologies.md). 

    Nella topologia di rete di esempio precedente esistono tre aree di rete, ognuna con un sito centrale di Skype for Business Server che gestisce CAC. Il sito centrale appropriato per un'area geografica di rete viene scelto dalle vicinanze geografiche. Poiché il traffico multimediale sarà più pesante nelle aree di rete, la proprietà per le vicinanze geografiche lo rende autonomo e continuerà a essere funzionante anche se altri siti centrali diventano non disponibili. 

    In questo esempio, una distribuzione Skype for business denominata Chicago è il sito centrale per l'area Nord America.

    Tutti gli utenti di Skype for business in Nord America sono ospitati nei server della distribuzione di Chicago. La tabella seguente mostra i siti centrali per tutte e tre le aree di rete.

    **Aree di rete e relativi siti centrali associati**

    |**Area di rete**|**Sito centrale**|
    |:-----|:-----|
    |America del Nord  <br/> |Chicago  <br/> |
    |EMEA  <br/> |Londra  <br/> |
    |APAC  <br/> |Pechino  <br/> |

    > [!NOTE]
    > A seconda della topologia di Skype for Business Server, è possibile assegnare lo stesso sito centrale a più aree di rete. 

3. Per ogni area geografica di rete, identificare tutti i siti di rete (uffici o posizioni) le cui connessioni WAN non sono vincolate da larghezza di banda. Poiché questi siti non sono vincolati alla larghezza di banda, non è necessario applicare i criteri di larghezza di banda CAC.

    Nell'esempio illustrato nella tabella seguente tre siti di rete non dispongono di collegamenti WAN con larghezza di banda limitata: New York, Chicago e Detroit.

   **Siti di rete non vincolati dalla larghezza di banda WAN**


   | **Sito di rete** | **Area di rete**   |
   |:-----------------|:---------------------|
   | New York  <br/>  | America del Nord  <br/> |
   | Chicago  <br/>   | America del Nord  <br/> |
   | Detroit  <br/>   | America del Nord  <br/> |


4. Per ogni area geografica di rete, identificare tutti i siti di rete che si connettono all'area di rete tramite collegamenti WAN con larghezza di banda limitata.

    Per garantire la qualità audio e video, è consigliabile che i siti di rete con vincoli di larghezza di banda dispongano delle WAN monitorate e dei criteri di larghezza di banda CAC che limitano il flusso di traffico multimediale (vocale o video) da e verso l'area di rete.

    Nell'esempio illustrato nella tabella seguente sono disponibili tre siti di rete vincolati da larghezza di banda WAN: Portland, Reno e Albuquerque.

   **Siti di rete vincolati da larghezza di banda WAN**

   |**Sito di rete**|**Area di rete**|
   |:-----|:-----|
   |Albuquerque  <br/> |America del Nord  <br/> |
   |Reno  <br/> |America del Nord  <br/> |
   |Portland  <br/> |America del Nord  <br/> |

   **Area di rete CAC Nord America con tre siti di rete non vincolati per larghezza di banda (Chicago, New York e Detroit) e tre siti di rete vincolati dalla larghezza di banda WAN (Portland, Reno e Albuquerque)**

     ![Siti di rete di esempio vincolati dalla larghezza di banda WAN](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. Per ogni collegamento WAN con larghezza di banda limitata, determinare le operazioni seguenti:

   - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causa il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.

   - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee. Se una nuova sessione video causa il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si vuole impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.

     **Siti di rete con informazioni sui vincoli di larghezza di banda WAN (larghezza di banda in Kbps)**


     | **Sito di rete**   | **Area di rete**   | **Limite di BW**      | **Limite audio**   | **Limite della sessione audio** | **Limite video**   | **Limite di sessione video** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | America del Nord  <br/> | 5.000  <br/>      | 2.000  <br/>      | 175  <br/>              | 1.400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | America del Nord  <br/> | 10.000  <br/>     | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              |
     | Portland  <br/>    | America del Nord  <br/> | 5.000  <br/>      | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              |
     | New York  <br/>    | America del Nord  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       |
     | Chicago  <br/>     | America del Nord  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       |
     | Detroit  <br/>     | America del Nord  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       |


6. Per ogni subnet della rete, specificare il sito di rete associato.

    > [!IMPORTANT]
    > Ogni subnet della rete deve essere associata a un sito di rete, anche se il sito di rete non è vincolato alla larghezza di banda. Questo perché il controllo di ammissione delle chiamate usa le informazioni sulla subnet per determinare in quale sito di rete si trova un endpoint. Quando vengono determinate le posizioni di entrambe le parti della sessione, il controllo di ammissione delle chiamate può determinare se è disponibile una larghezza di banda sufficiente per stabilire una chiamata. Quando viene stabilita una sessione su un collegamento che non contiene limiti di larghezza di banda, viene generato un avviso. 

    > [!IMPORTANT]
    > Se si distribuiscono server Edge audio/video, gli indirizzi IP pubblici di ogni Edge Server devono essere associati al sito di rete in cui è distribuito il server perimetrale. Ogni indirizzo IP pubblico di un/V Edge Server deve essere aggiunto alle impostazioni di configurazione della rete come subnet con una subnet mask di 32. Ad esempio, se si distribuisce un/V Edge Server a Chicago, per ogni indirizzo IP esterno di questi server è possibile creare una subnet con una subnet mask di 32 e associare il sito di rete a Chicago con tali subnet. Per informazioni dettagliate sugli indirizzi IP pubblici, vedere [pianificare i requisiti di rete per Skype for business](../../plan-your-deployment/network-requirements/network-requirements.md). 

    Viene generato un avviso KHI (Key Health Indicator), che specifica un elenco di indirizzi IP presenti nella rete, ma che non sono associati a una subnet oppure che la subnet che include gli indirizzi IP non è associata a un sito di rete. Questo avviso non verrà generato più di una volta entro un periodo di 8 ore. Di seguito sono riportate le informazioni relative agli avvisi e un esempio:

    **Origine**: CS Bandwidth Policy Service (Core) 

    **Numero evento**: 36034

    **Livello**: 2

    **Descrizione**: le subnet per gli indirizzi IP seguenti: \<l'elenco di indirizzi\> IP non è configurato o le subnet non sono associate a un sito di rete. 

    **Causa**: le subnet per gli indirizzi IP corrispondenti mancano alle impostazioni di configurazione della rete o le subnet non sono associate a un sito di rete. 

    **Risoluzione**: aggiungere subnet che corrispondono all'elenco precedente di indirizzi IP nelle impostazioni di configurazione della rete e associare ogni subnet a un sito di rete.

    Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete. Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema come segue:

    un. Assicurarsi che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.

    b. Assicurarsi che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate a un sito di rete.

   **Siti di rete e subnet associate (larghezza di banda in Kbps)**


   | **Sito di rete**   | **Area di rete**   | **Limite di BW**      | **Limite audio**   | **Limite della sessione audio** | **Limite video**   | **Limite di sessione video** | **Subnet**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | America del Nord  <br/> | 5.000  <br/>      | 2.000  <br/>      | 175  <br/>              | 1.400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | America del Nord  <br/> | 10.000  <br/>     | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | Portland  <br/>    | America del Nord  <br/> | 5.000  <br/>      | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | New York  <br/>    | America del Nord  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Chicago  <br/>     | America del Nord  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | Detroit  <br/>     | America del Nord  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. Nel controllo di ammissione alle chiamate di Skype for Business Server le connessioni tra le aree di rete sono chiamate collegamenti di area geografica. Per ogni collegamento all'area geografica, determinare quanto segue, come per i siti di rete:

   - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causa il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.

   - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee. Se una nuova sessione video causa il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si vuole impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.

   **Collegamenti all'area di rete con limiti di larghezza di banda associati**

     ![Esempio di limitazioni fra tre aree](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **Informazioni sulla larghezza di banda del collegamento geografica (larghezza di banda in Kbps)**


   | **Nome collegamento area geografica**  | **First Region**     | **Second Region** | **Limite di BW**  | **Limite audio** | **Limite della sessione audio** | **Limite video** | **Limite di sessione video** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | NA-EMEA-COLLEGAMENTO  <br/>   | America del Nord  <br/> | EMEA  <br/>       | 50.000  <br/> | 20.000  <br/>   | 175  <br/>              | 14.000  <br/>   | 700  <br/>              |
   | EMEA-APAC-COLLEGAMENTO  <br/> | EMEA  <br/>          | APAC  <br/>       | 25.000  <br/> | 10.000  <br/>   | 175  <br/>              | 7.000  <br/>    | 700  <br/>              |


8. Definire una route tra ogni coppia di aree di rete.

    > [!NOTE]
    > Sono necessari due collegamenti per la route tra il Nord America e le aree APAC perché non è presente un collegamento all'area geografica che li connette direttamente. 

   **Route di area geografica**


   | **Nome route dell'area geografica**  | **First Region**     | **Second Region** | **Collegamenti all'area geografica**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | NA-EMEA-ROUTE  <br/>   | America del Nord  <br/> | EMEA  <br/>       | NA-EMEA-COLLEGAMENTO  <br/>                 |
   | EMEA-APAC-ROUTE  <br/> | EMEA  <br/>          | APAC  <br/>       | EMEA-APAC-COLLEGAMENTO  <br/>               |
   | NA-APAC-ROUTE  <br/>   | America del Nord  <br/> | APAC  <br/>       | NA-EMEA-LINK, EMEA-APAC-LINK  <br/> |


9. Per ogni coppia di siti di rete collegati direttamente da un singolo collegamento (denominato collegamento tra siti), determinare le operazioni seguenti:

     - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causa il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

     - Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.

     - Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee. Se una nuova sessione video causa il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

     - Limite di larghezza di banda che si vuole impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.

   **Area di rete CAC Nord America che mostra le capacità di larghezza di banda e i limiti di larghezza di banda per il collegamento tra siti tra Reno e Albuquerque**

     ![Esempio di siti di rete vincolati dalla larghezza di banda WAN](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **Informazioni sulla larghezza di banda per un collegamento intersito tra due siti di rete (larghezza di banda in Kbps)**

   |**Nome collegamento tra siti**|**Primo sito**|**Secondo sito**|**Limite di BW**|**Limite audio**|**Limite della sessione audio**|**Limite video**|**Limite di sessione video**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-albu-collegamento intersito  <br/> |Reno  <br/> |Albuquerque  <br/> |20.000  <br/> |12.000  <br/> |175  <br/> |5.000  <br/> |700  <br/> |

### <a name="next-steps"></a>Operazioni successive

Dopo aver raccolto le informazioni necessarie, è possibile eseguire la distribuzione di CAC usando il pannello di controllo di Skype for Business Server Management Shell o Skype for Business Server.

> [!NOTE]
> Anche se è possibile eseguire la maggior parte delle attività di configurazione della rete usando il pannello di controllo di Skype for Business Server, per creare subnet e collegamenti intersito, è necessario usare Skype for Business Server Management Shell. Per informazioni dettagliate, vedere [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps) e [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps). 


