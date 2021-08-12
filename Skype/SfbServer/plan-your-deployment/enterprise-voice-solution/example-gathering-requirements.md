---
title: Esempio Raccolta di requisiti per il controllo di ammissione di chiamata in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Viene fornito un esempio dettagliato di pianificazione del controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale, inclusa la raccolta di informazioni sui siti, le aree geografiche e la larghezza di banda della rete.
ms.openlocfilehash: 47f44f6b20779cce80c5499eb792945276fec7144fb7661e8aca8ce97e1e09ae
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324126"
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>Esempio: Raccolta dei requisiti per il controllo di ammissione di chiamata in Skype for Business Server

Viene fornito un esempio dettagliato di pianificazione del controllo di ammissione di chiamata in Skype for Business Server VoIP aziendale, inclusa la raccolta di informazioni sui siti, le aree geografiche e la larghezza di banda della rete.

In questo esempio viene illustrato come pianificare e implementare il servizio Controllo di ammissione di chiamata (CAC). A livello generale, sono previste le attività seguenti:

1. Identificare tutti gli hub e le backbone di rete (note come aree di rete).

2. Identificare il Skype for Business Server centrale che gestirà il controllo di ammissione di chiamata per ogni area di rete.

3. Identificare e definire i siti di rete connessi a ogni area di rete.

4. Per ogni sito di rete la cui connessione alla rete WAN è vincolata dalla larghezza di banda, descrivere la capacità della larghezza di banda della connessione WAN e i limiti di larghezza di banda impostati dall'amministratore di rete per il traffico multimediale Skype for Business Server, se applicabile. Non è necessario includere siti con connessione alla WAN non soggetta a vincoli di larghezza di banda.

5. Associare ogni subnet della rete a un sito di rete.

6. Eseguire il mapping dei collegamenti tra le aree di rete. Per ogni collegamento, descrivere la capacità della larghezza di banda e gli eventuali limiti che l'amministratore di rete ha posto Skype for Business Server traffico multimediale.

7. Definire una route tra ogni coppia di aree di rete.

## <a name="gather-the-required-information"></a>Raccogliere le informazioni necessarie

Per la preparazione per il servizio Controllo di ammissione di chiamata, raccogliere le informazioni descritte nei passaggi seguenti:

1. Identificare le aree di rete. Un'area di rete rappresenta una backbone o un hub di rete. 

    Una backbone o un hub di rete è una parte dell'infrastruttura della rete del computer che interconnette diverse parti della rete, fornendo un percorso per lo scambio di informazioni tra diverse LAN o subnet. Una backbone può unire reti diverse, da una piccola postazione a un'area geografica estesa. La capacità della backbone è in genere superiore a quella delle reti a essa connesse.

    Nella topologia di esempio sono presenti tre aree di rete: Nord America, EMEA e APAC. In un'area di rete è contenuto un insieme di siti di rete. Consultarsi con l'amministratore di rete per definire le aree di rete dell'organizzazione.

2. Identificare il sito centrale associato a ogni area di rete. Un sito centrale contiene almeno un Front End Server ed è la distribuzione di Skype for Business Server che gestirà il controllo di ammissione di chiamata per tutto il traffico multimediale che passa attraverso la connessione WAN dell'area di rete.

   **Rete aziendale di esempio divisa in tre aree di rete**

     ![Esempio di topologia di rete con 3 aree di rete](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > Una rete Multiprotocol Label Switching (MPLS) dovrebbe essere rappresentata come area di rete in cui a ogni posizione geografica corrisponde un sito di rete. Per informazioni dettagliate, [vedere Components and topologies for call admission control in Skype for Business](components-and-topologies.md). 

    Nella topologia di rete di esempio precedente sono presenti tre aree di rete, ognuna con Skype for Business Server sito centrale che gestisce il controllo di ammissione di chiamata. Il sito centrale appropriato per un'area di rete viene scelto in base alla vicinanza geografica. Poiché il traffico multimediale sarà più intenso all'interno delle aree di rete, la proprietà per vicinanza geografica rende il traffico autonomo e ne garantisce il funzionamento anche in caso di non disponibilità degli altri siti centrali. 

    In questo esempio, una distribuzione Skype for Business denominata Chicago è il sito centrale per l'area Nord America.

    Tutti Skype for Business utenti del Nord America sono ospitati in server nella distribuzione di Chicago. Nella tabella seguente sono elencati i siti centrali per tutte e tre le aree di rete.

    **Aree di rete e siti centrali associati**

    |**Area di rete**|**Sito centrale**|
    |:-----|:-----|
    |Nord America  <br/> |Chicago  <br/> |
    |EMEA  <br/> |Londra  <br/> |
    |APAC  <br/> |Pechino  <br/> |

    > [!NOTE]
    > A seconda della topologia Skype for Business Server, lo stesso sito centrale può essere assegnato a più aree di rete. 

3. Per ogni area di rete, identificare tutti i siti di rete (uffici o postazioni) le cui connessioni WAN non siano vincolate dalla larghezza di banda. Poiché questi siti non sono vincolati dalla larghezza di banda, non è necessario applicare criteri di larghezza di banda del servizio Controllo di ammissione di chiamata.

    Nell'esempio illustrato nella tabella seguente tre siti di rete non dispongono di collegamenti WAN con vincoli di larghezza di banda: New York, Chicago e Detroit.

   **Siti di rete non vincolati dalla larghezza di banda della WAN**


   | **Sito di rete** | **Area di rete**   |
   |:-----------------|:---------------------|
   | New York  <br/>  | Nord America  <br/> |
   | Chicago  <br/>   | Nord America  <br/> |
   | Detroit  <br/>   | Nord America  <br/> |


4. Per ogni area di rete identificare tutti i siti di rete che si connettono all'area di rete mediante collegamenti WAN con vincoli di larghezza di banda.

    Per garantire la qualità audio e video, è consigliabile fare in modo che le WAN dei siti di rete con vincoli di larghezza di banda siano monitorate e applicare criteri di larghezza di banda del servizio Controllo di ammissione di chiamata che limitino il flusso del traffico multimediale (vocale o video) scambiato con l'area di rete.

    Nell'esempio illustrato nella tabella seguente sono presenti tre siti di rete vincolati dalla larghezza di banda della WAN: Portland, Reno e Albuquerque.

   **Siti di rete vincolati dalla larghezza di banda della WAN**

   |**Sito di rete**|**Area di rete**|
   |:-----|:-----|
   |Albuquerque  <br/> |Nord America  <br/> |
   |Reno  <br/> |Nord America  <br/> |
   |Portland  <br/> |Nord America  <br/> |

   **Area di rete Nord America con servizio Controllo di ammissione di chiamata con tre siti di rete non vincolati dalla larghezza di banda (Chicago, New York e Detroit) e tre siti di rete vincolati dalla larghezza di banda della WAN (Portland, Reno e Albuquerque)**

     ![Siti di rete di esempio vincolati dalla larghezza di banda WAN](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. Per ogni collegamento WAN con vincoli di larghezza di banda, determinare quanto segue:

   - Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causerà il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si desidera impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 175 kbps, ma può essere modificato dall'amministratore.

   - Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni video simultanee. Se una nuova sessione video causerà il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si desidera impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 700 kbps, ma può essere modificato dall'amministratore.

     **Siti di rete con informazioni sui vincoli della larghezza di banda della WAN (larghezza di banda in kbps)**


     | **Sito di rete**   | **Area di rete**   | **Limite di larghezza di banda**      | **Limite audio**   | **Limite sessione audio** | **Limite video**   | **Limite sessione video** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | Nord America  <br/> | 5.000  <br/>      | 2.000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | Nord America  <br/> | 10,000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | Portland  <br/>    | Nord America  <br/> | 5.000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | New York  <br/>    | Nord America  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       |
     | Chicago  <br/>     | Nord America  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       |
     | Detroit  <br/>     | Nord America  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       |


6. Per ogni subnet della rete, specificare il sito di rete associato.

    > [!IMPORTANT]
    > Ogni subnet della rete deve essere associata a un sito di rete, anche se non vincolato dalla larghezza di banda, poiché il servizio Controllo di ammissione di chiamata utilizza le informazioni delle subnet per determinate il sito di rete in cui è posizionato un endpoint. Dopo che sono state determinate le posizioni in entrambe le parti della sessione, il servizio Controllo di ammissione di chiamata può determinare se la larghezza di banda è sufficiente per stabilire una chiamata. Quando viene stabilita una sessione su un collegamento senza limiti di larghezza di banda, viene generato un avviso. 

    > [!IMPORTANT]
    > Se si distribuiscono Audio/Video Edge Server, gli indirizzi IP pubblici di ognuno di questi server deve essere associato al sito di rete in cui è distribuito il server. Ogni indirizzo IP pubblico dell'A/V Edge Server deve essere aggiunto alle impostazioni di configurazione di rete come subnet con subnet mask 32. Se ad esempio si distribuiscono A/V Edge Server nel sito di Chicago, creare per ogni indirizzo IP esterno di tali server una subnet con subnet mask 32 e associare il sito di rete Chicago a tali subnet. Per informazioni dettagliate sugli indirizzi IP pubblici, vedere [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md). 

    Viene generato un avviso Key Health Indicator (KHI) in cui viene specificato un elenco di indirizzi IP presenti nella rete che non sono associati a una subnet oppure la cui subnet non è associata a un sito di rete. Questo avviso viene generato una sola volta ogni 8 ore. Di seguito vengono riportati un esempio e le informazioni rilevanti dell'avviso:

    **Origine**: Servizio criteri larghezza di banda LS (Core) 

    **Numero evento**: 36034

    **Livello**: 2

    **Descrizione:** le subnet per i seguenti indirizzi IP: non sono configurate o le subnet non sono \<List of IP Addresses\> associate a un sito di rete. 

    **Causa**: le subnet per gli indirizzi IP corrispondenti non sono presenti nelle impostazioni della configurazione di rete oppure non sono associate a un sito di rete. 

    **Soluzione**: aggiungere le subnet per gli indirizzi IP corrispondenti alle impostazioni della configurazione di rete e associare ogni subnet a un sito di rete.

    Se ad esempio nell'elenco di indirizzi IP nell'avviso sono specificati sia 10.121.248.226 che 10.121.249.20, questi indirizzi IP non sono associati a una subnet oppure la subnet a cui sono associati non appartiene a un sito di rete. Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema in questo modo:

    a. Verificare che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e che l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.

    b. Verificare che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate ognuna a un sito di rete.

   **Siti di rete e subnet associate (larghezza di banda in kbps)**


   | **Sito di rete**   | **Area di rete**   | **Limite di larghezza di banda**      | **Limite audio**   | **Limite sessione audio** | **Limite video**   | **Limite sessione video** | **Subnet**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | Nord America  <br/> | 5.000  <br/>      | 2.000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | Nord America  <br/> | 10,000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | Portland  <br/>    | Nord America  <br/> | 5.000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | New York  <br/>    | Nord America  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Chicago  <br/>     | Nord America  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | Detroit  <br/>     | Nord America  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/> | (nessun limite)  <br/>       | (nessun limite)  <br/> | (nessun limite)  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. In Skype for Business Server di ammissione di chiamata, le connessioni tra aree di rete sono denominate collegamenti di area. Come per i siti di rete, determinare per ogni collegamento area gli aspetti seguenti:

   - Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causerà il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si desidera impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 175 kbps, ma può essere modificato dall'amministratore.

   - Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni video simultanee. Se una nuova sessione video causerà il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

   - Limite di larghezza di banda che si desidera impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 700 kbps, ma può essere modificato dall'amministratore.

   **Collegamenti aree di rete con limiti di larghezza di banda associati**

     ![Esempio di limitazioni tra 3 aree geografiche](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **Informazioni sulla larghezza di banda dei collegamenti aree (larghezza di banda in kbps)**


   | **Nome collegamento area**  | **Prima area**     | **Seconda area** | **Limite di larghezza di banda**  | **Limite audio** | **Limite sessione audio** | **Limite video** | **Limite sessione video** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | NA-EMEA-LINK  <br/>   | Nord America  <br/> | EMEA  <br/>       | 50.000  <br/> | 20.000  <br/>   | 175  <br/>              | 14,000  <br/>   | 700  <br/>              |
   | EMEA-APAC-LINK  <br/> | EMEA  <br/>          | APAC  <br/>       | 25.000  <br/> | 10,000  <br/>   | 175  <br/>              | 7,000  <br/>    | 700  <br/>              |


8. Definire una route tra ogni coppia di aree di rete.

    > [!NOTE]
    > Sono necessari due collegamenti per la route tra le aree Nord America e APAC poiché non sono connesse direttamente tramite un collegamento area. 

   **Route aree**


   | **Nome route area**  | **Prima area**     | **Seconda area** | **Collegamenti aree**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | NA-EMEA-ROUTE  <br/>   | Nord America  <br/> | EMEA  <br/>       | NA-EMEA-LINK  <br/>                 |
   | EMEA-APAC-ROUTE  <br/> | EMEA  <br/>          | APAC  <br/>       | EMEA-APAC-LINK  <br/>               |
   | NA-APAC-ROUTE  <br/>   | Nord America  <br/> | APAC  <br/>       | COLLEGAMENTO-NA-EMEA, COLLEGAMENTO-EMEA-APAC  <br/> |


9. Per ogni coppia di siti di rete direttamente connessi tramite un collegamento singolo, denominato collegamento tra siti, determinare quanto segue:

     - Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni audio simultanee. Se una nuova sessione audio causerà il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

     - Limite di larghezza di banda che si desidera impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 175 kbps, ma può essere modificato dall'amministratore.

     - Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni video simultanee. Se una nuova sessione video causerà il superamento di questo limite, Skype for Business Server non consente l'avvio della sessione.

     - Limite di larghezza di banda che si desidera impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 700 kbps, ma può essere modificato dall'amministratore.

   **Area di rete Nord America con servizio Controllo di ammissione di chiamata in cui vengono indicate le capacità di larghezza di banda e i limiti di larghezza di banda per il collegamento tra siti tra Reno e Albuquerque**

     ![Esempio di siti di rete vincolati dalla larghezza di banda WAN](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **Informazioni sulla larghezza di banda per un collegamento tra siti tra due siti di rete (larghezza di banda in kbps)**

   |**Nome collegamento tra siti**|**Primo sito**|**Secondo sito**|**Limite di larghezza di banda**|**Limite audio**|**Limite sessione audio**|**Limite video**|**Limite sessione video**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20.000  <br/> |12,000  <br/> |175  <br/> |5.000  <br/> |700  <br/> |

### <a name="next-steps"></a>Operazioni successive

Dopo aver raccolto le informazioni necessarie, è possibile eseguire la distribuzione del controllo di ammissione di chiamata utilizzando Skype for Business Server Management Shell o Skype for Business Server Pannello di controllo.

> [!NOTE]
> Sebbene sia possibile eseguire la maggior parte delle attività di configurazione di rete utilizzando il Pannello di controllo di Skype for Business Server, per creare subnet e collegamenti tra siti, è necessario utilizzare Skype for Business Server Management Shell. Per informazioni dettagliate, [vedere New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps) e [New-CsNetworkInterSitePolicy.](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)