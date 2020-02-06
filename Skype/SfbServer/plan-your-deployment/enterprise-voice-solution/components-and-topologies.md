---
title: Componenti e topologie per il controllo di ammissione di chiamata in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Pianificazione del controllo di ammissione alle chiamate (CAC) se si ha una rete MPLS, un trunk SIP o un gateway PSTN o un PBX di terze parti. Si applica a Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 7fcbc3e8c7fc7b4139fd9c83718db59af099f47f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803116"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Componenti e topologie per il controllo di ammissione di chiamata in Skype for business

Pianificazione del controllo di ammissione alle chiamate (CAC) se si ha una rete MPLS, un trunk SIP o un gateway PSTN o un PBX di terze parti. Si applica a Skype for Business Server VoIP aziendale.

Gli argomenti di questa sezione contengono informazioni sulle considerazioni speciali per la distribuzione del controllo di ammissione di chiamata (CAC) con vari tipi di topologie di rete.

## <a name="call-admission-control-on-an-mpls-network"></a>Controllo di ammissione delle chiamate in una rete MPLS

In una rete di commutazione di etichette Multiprotocol (MPLS), tutti i siti sono connessi da una mesh completa. Ossia, tutti i siti sono connessi direttamente alla backbone MPLS del provider di servizi Internet e ogni sito è il provisioning della larghezza di banda da usare in un collegamento WAN al cloud MPLS. Non esiste un hub di rete o un sito centrale per controllare il routing IP. La figura seguente mostra una rete semplice basata sulla tecnologia MPLS.

**Esempio di rete MPLS**

![Controllo di ammissione di chiamata con MPLS](../../media/CAC_MPLS_1.jpg)

Per distribuire il controllo di ammissione di chiamata (CAC) in una rete MPLS, è possibile creare un'area di rete per rappresentare il cloud MPLS e creare un sito di rete per rappresentare ogni sito satellite MPLS. Nella figura seguente viene illustrato il modo in cui i siti della rete e della rete devono essere configurati per rappresentare la rete MPLS di esempio nella figura precedente. I limiti generali della larghezza di banda e i limiti della sessione di larghezza di banda si basano sulla capacità del collegamento WAN da ogni sito di rete all'area di rete che rappresenta il cloud MPLS.

**Area geografica e siti di rete per una rete MPLS**

![Diagramma del controllo di ammissione di chiamata con MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>Controllo di ammissione di chiamata in un trunk SIP

Per distribuire il controllo di ammissione di chiamata (CAC) in un trunk SIP, è possibile creare un sito di rete per rappresentare il provider del servizio di telefonia Internet (ITSP). Per applicare i valori dei criteri di larghezza di banda nel trunk SIP, è possibile creare un criterio tra siti tra il sito di rete dell'organizzazione e il sito di rete creato per rappresentare il ITSP.

La figura seguente mostra un esempio di distribuzione di CAC in un trunk SIP.

**Configurazione di CAC in un trunk SIP**

![Diagramma del trunking SIP del controllo di ammissione di chiamata](../../media/CAC_SIP_trunk_1.jpg)

Per configurare CAC in un trunk SIP, sarà necessario eseguire le attività seguenti durante la distribuzione di CAC:

1. Creare un sito di rete per rappresentare il ITSP. Associa il sito di rete a un'area di rete appropriata e assegna la larghezza di banda pari a zero per l'audio e il video per questo sito di rete. Per informazioni dettagliate, vedere [configurare i siti di rete per CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) nella documentazione relativa alla distribuzione.

    > [!NOTE]
    > Per ITSP, questa configurazione del sito di rete non è funzionale. I valori dei criteri di larghezza di banda vengono effettivamente applicati nel passaggio 2.

2. Creare un collegamento tra siti per il trunk SIP usando i valori di parametro rilevanti per il sito creato nel passaggio 1. Ad esempio, usa il nome del sito di rete nell'organizzazione come valore del parametro NetworkSiteID1 e il sito di rete ITSP come valore del parametro NetworkSiteID2. Per informazioni dettagliate, vedere [creare criteri di intersito di rete in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) nella documentazione di distribuzione e [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).

3. Ottenere l'indirizzo IP del punto di terminazione multimediale della sessione (SCB) del controller di bordo del ITSP. Aggiungere l'indirizzo IP con una subnet mask di 32 al sito di rete che rappresenta il ITSP. Per informazioni dettagliate, vedere [associare una subnet a un sito di rete](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Controllo di ammissione di chiamata con un PBX o un gateway PSTN di terze parti

Questo argomento descrive alcuni esempi di come il controllo di ammissione di chiamata (CAC) può essere distribuito sul collegamento tra l'interfaccia gateway di Mediation Server e un gateway PSTN (Public Branch Exchange Network) di terze parti o un PBX privato.

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Caso 1: CAC tra il Mediation Server e un gateway PSTN

CAC può essere distribuito sul collegamento WAN dall'interfaccia gateway di Mediation Server a un gateway PBX o PSTN di terze parti.

**Caso 1: CAC tra il Mediation Server e un gateway PSTN**

![Caso 1: controllo di ammissione di chiamata tra il Mediation Server e un gateway PSTN](../../media/CAC_gateways_1.jpg)

In questo esempio, CAC viene applicato tra il Mediation Server e un gateway PSTN. Se un utente del client Skype for business nel sito di rete 1 effettua una chiamata PSTN tramite il gateway PSTN nel sito di rete 2, il contenuto multimediale passa attraverso il collegamento WAN. Vengono pertanto eseguiti due controlli CAC per ogni sessione PSTN:

- Tra l'applicazione client Skype for business e il Mediation Server

- Tra il Mediation Server e il gateway PSTN

Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un'applicazione client nel sito di rete 1.

> [!NOTE]
> Verificare che la subnet IP a cui appartiene il gateway PSTN sia configurata e associata al sito di rete 2.

> [!NOTE]
> Verificare che la subnet IP a cui appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.

> [!NOTE]
> Per informazioni dettagliate, vedere [associare una subnet a un sito di rete](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Caso 2: CAC tra il Mediation Server e un PBX di terze parti con il punto di terminazione multimediale

Questa configurazione è simile al caso 1. In entrambi i casi, il Mediation Server sa quale dispositivo termina il contenuto multimediale all'estremità opposta del collegamento WAN e l'indirizzo IP del gateway PSTN o del PBX con il punto di terminazione multimediale (MTP) è configurato nel server Mediation come hop successivo.

**Caso 2: CAC tra il Mediation Server e un PBX di terze parti con MTP**

![Caso 2: controllo di ammissione di chiamata tra il Mediation Server e un PBX con MTP](../../media/CAC_gateways_2.jpg)

In questo esempio, CAC viene applicato tra il Mediation Server e il PBX/MTP. Se un utente del client Skype for Business presso il sito di rete 1 effettua una chiamata PSTN tramite il PBX/MTP situato nel sito di rete 2, il flusso multimediale passa attraverso il collegamento WAN. Pertanto, per ogni sessione PSTN vengono eseguiti due controlli CAC:

- Tra l'applicazione client Skype for business e il Mediation Server

- Tra il Mediation Server e il PBX/MTP

Questo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un client nel sito di rete 1.

> [!NOTE]
> Verificare che la subnet IP a cui appartiene il MTP sia configurata e associata al sito di rete 2.

> [!NOTE]
> Verificare che la subnet IP a cui appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.

> [!NOTE]
> Per informazioni dettagliate, vedere [associare una subnet a un sito di rete](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza un punto di interruzione multimediale

Il caso 3 è leggermente diverso dai primi due casi. Se non c'è un MTP nel PBX di terze parti, per una richiesta di sessione in uscita al PBX di terze parti, il Mediation Server non sa dove verranno terminati i contenuti multimediali nel limite del PBX. In questo caso, il contenuto multimediale passa direttamente tra il Mediation Server e il dispositivo endpoint di terze parti.

**Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza MTP**

![Caso 3: controllo di ammissione di chiamata tra il Mediation Server e un PBX senza MTP](../../media/CAC_gateways_3.jpg)

In questo esempio, se un utente del client Skype for Business presso il sito di rete 1 effettua una chiamata a un utente tramite il PBX, il Mediation Server è in grado di eseguire controlli CAC solo sulla gamba del proxy (tra l'applicazione client Skype for business e il Mediation Server). Poiché il Mediation Server non contiene informazioni sul dispositivo endpoint durante la richiesta della sessione, non è possibile eseguire controlli CAC sul collegamento WAN (tra il Mediation Server e l'endpoint di terze parti) prima di chiamare establishment. Dopo aver stabilito la sessione, tuttavia, il Mediation Server facilita la contabilizzazione della larghezza di banda usata nel trunk.

Per le chiamate che derivano dall'endpoint di terze parti, le informazioni relative al dispositivo endpoint sono disponibili al momento della richiesta di sessione e il controllo CAC può essere eseguito su entrambi i lati del Mediation Server.

> [!NOTE]
> Verificare che la subnet IP a cui appartengono i dispositivi endpoint sia configurata e associata al sito di rete 2.

> [!NOTE]
> Verificare che la subnet IP a cui appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.

> [!NOTE]
> Per informazioni dettagliate, vedere [associare una subnet a un sito di rete](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).


