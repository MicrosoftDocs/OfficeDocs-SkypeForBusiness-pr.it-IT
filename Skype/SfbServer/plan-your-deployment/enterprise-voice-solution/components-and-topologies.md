---
title: Componenti e topologie per il controllo di ammissione di chiamata in Skype for business
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
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Pianificazione del controllo di ammissione di chiamata (CAC) se si dispone di una rete MPLS, un trunk SIP o un gateway PSTN o un PBX di terze parti. Si applica a Skype for Business Server VoIP aziendale.
ms.openlocfilehash: e40525121020259a40f10d90cd79d70aaa749ac3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825846"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Componenti e topologie per il controllo di ammissione di chiamata in Skype for business

Pianificazione del controllo di ammissione di chiamata (CAC) se si dispone di una rete MPLS, un trunk SIP o un gateway PSTN o un PBX di terze parti. Si applica a Skype for Business Server VoIP aziendale.

Negli argomenti di questa sezione vengono fornite informazioni sulle considerazioni speciali di cui tenere conto per la distribuzione del servizio Controllo di ammissione di chiamata con diversi tipi di topologie di rete.

## <a name="call-admission-control-on-an-mpls-network"></a>Controllo di ammissione di chiamata su una rete MPLS

In una rete MPLS (Multiprotocol Label Switching) tutti i siti sono connessi tramite full mesh, ovvero tutti i siti sono connessi direttamente alla dorsale MPLS del provider di servizi Internet e a ogni sito viene assegnata una larghezza di banda da utilizzare nel cloud MPLS attraverso un collegamento WAN. Non è presente alcun hub di rete o sito centrale per controllare il routing IP. Nella figura seguente viene illustrata una rete semplice basata sulla tecnologia MPLS.

**Rete MPLS di esempio**

![CAC con MPLS](../../media/CAC_MPLS_1.jpg)

Per distribuire il controllo di ammissione di chiamata in una rete MPLS, è necessario creare un'area di rete che rappresenti il cloud MPLS e un sito di rete che rappresenti ogni sito satellite MPLS. Nella figura seguente viene illustrato come è consigliabile configurare l'area di rete e i siti di rete per rappresentare la rete MPLS di esempio della figura precedente. I limiti di larghezza di banda totali e quelli di sessione sono quindi basati sulla capacità del collegamento WAN che va da ogni sito di rete all'area di rete che rappresenta il cloud MPLS.

**Area di rete e siti di rete per una rete MPLS**

![Controllo di ammissione di chiamata (CAC) con diagramma MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>Controllo di ammissione di chiamata in un trunk SIP

Per distribuire il servizio Controllo di ammissione di chiamata in un trunk SIP, creare un sito di rete per rappresentare il provider di servizi di telefonia Internet (ITSP). Per applicare i valori dei criteri di larghezza di banda nel trunk SIP, creare criteri tra siti tra il sito di rete dell'organizzazione e il sito di rete creato per rappresentare l'ITSP.

Nella figura seguente è illustrato un esempio di distribuzione del servizio Controllo di ammissione di chiamata in un trunk SIP.

**Configurazione del servizio Controllo di ammissione di chiamata in un trunk SIP**

![Diagramma del trunking SIP del controllo di ammissione di chiamata](../../media/CAC_SIP_trunk_1.jpg)

Per configurare il servizio Controllo di ammissione di chiamata in un trunk SIP, è necessario eseguire le operazioni seguenti durante la distribuzione del servizio:

1. Creare un sito di rete per rappresentare l'ITSP. Associare il sito di rete a un'area di rete appropriata e allocare una larghezza di banda pari a zero per audio e video per il sito di rete. Per informazioni dettagliate, vedere [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) nella documentazione relativa alla distribuzione.

    > [!NOTE]
    > Per l'ITSP, questa configurazione del sito di rete non è funzionale. I valori dei criteri di larghezza di banda vengono effettivamente applicati nel passaggio 2.

2. Creare un collegamento tra siti per il trunk SIP utilizzando i valori dei parametri rilevanti per il sito creato nel passaggio 1. Utilizzare, ad esempio, il nome del sito di rete dell'organizzazione come valore del parametro NetworkSiteID1 e il sito di rete dell'ITSP come valore del parametro NetworkSiteID2. Per informazioni dettagliate, vedere [creare criteri intersito di rete in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) nella documentazione relativa alla distribuzione e [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).

3. Ottenere l'indirizzo IP del punto di terminazione multimediale della sessione (SCB, Session Border Controller) dall'ITSP. Aggiungere tale indirizzo IP con una subnet mask di 32 al sito di rete che rappresenta l'ITSP. Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Controllo di ammissione di chiamata con un PBX o un gateway PSTN di terze parti

In questo argomento vengono descritti alcuni esempi del modo in cui il controllo di ammissione di chiamata può essere distribuito sul collegamento tra l'interfaccia gateway del Mediation Server e un gateway PSTN (Public Switched Telephone Network) di terze parti o un sistema PBX (Private Branch Exchange).

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Caso 1: CAC tra il Mediation Server e un gateway PSTN

È possibile distribuire il servizio di controllo di ammissione sul collegamento WAN dall'interfaccia del gateway del Mediation Server a un gateway PSTN o PBX di terze parti.

**Caso 1: CAC tra il Mediation Server e un gateway PSTN**

![Caso 1: CAC tra il gateway PSTN di Mediation Server](../../media/CAC_gateways_1.jpg)

In questo esempio viene applicato il servizio di controllo di ammissione tra il Mediation Server e un gateway PSTN. Se un utente del client Skype for business nel sito di rete 1 inserisce una chiamata PSTN tramite il gateway PSTN nel sito di rete 2, il file multimediale scorre attraverso il collegamento WAN. Pertanto, vengono eseguiti due controlli CAC per ogni sessione PSTN:

- Tra l'applicazione client Skype for business e il Mediation Server

- Tra il Mediation Server e il gateway PSTN

Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un'applicazione client nel sito di rete 1.

> [!NOTE]
> Verificare che la subnet IP a cui appartiene il gateway PSTN sia configurata e associata a sito di rete 2.

> [!NOTE]
> Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.

> [!NOTE]
> Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Caso 2: CAC tra il Mediation Server e un PBX di terze parti con il punto di terminazione multimediale

Questa configurazione è simile al caso 1. In entrambi i casi, il Mediation Server sa quale dispositivo termina i file multimediali all'estremità opposta del collegamento WAN e l'indirizzo IP del gateway PSTN o del PBX con il punto di terminazione multimediale è configurato sul Mediation Server come hop successivo.

**Caso 2: CAC tra il Mediation Server e un PBX di terze parti con MTP**

![Caso 2: CAC tra Mediation Server PBX con MTP](../../media/CAC_gateways_2.jpg)

In questo esempio viene applicato il servizio di controllo di ammissione tra il Mediation Server e il sistema PBX/MTP. Se un utente del client Skype for business nel sito di rete 1 inserisce una chiamata PSTN tramite il sistema PBX/MTP che si trova nel sito di rete 2, il file multimediale scorre attraverso il collegamento WAN. Pertanto, per ogni sessione PSTN vengono eseguiti due controlli CAC:

- Tra l'applicazione client Skype for business e il Mediation Server

- Tra il Mediation Server e il sistema PBX/MTP

Questo metodo funziona sia per le chiamate PSTN in arrivo a un client nel sito di rete 1 che per le chiamate PSTN in uscita provenienti da un client nel sito di rete 1.

> [!NOTE]
> Verificare che la subnet IP a cui appartiene il MTP sia configurata e associata al sito di rete 2.

> [!NOTE]
> Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.

> [!NOTE]
> Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza un punto di terminazione multimediale

Il caso 3 è leggermente diverso rispetto ai primi due casi. Se non è presente alcun MTP sul PBX di terze parti, per una richiesta di sessione in uscita al sistema PBX di terze parti, il Mediation Server non sa dove i contenuti multimediali verranno terminati nel limite del PBX. In questo caso, il contenuto multimediale scorre direttamente tra il Mediation Server e il dispositivo endpoint di terze parti.

**Caso 3: CAC tra il Mediation Server e un PBX di terze parti senza MTP**

![Caso 3: CAC tra Mediation Server PBX no MTP](../../media/CAC_gateways_3.jpg)

In questo esempio, se un utente del client Skype for business nel sito di rete 1 inserisce una chiamata a un utente tramite il sistema PBX, Mediation Server è in grado di eseguire controlli CAC solo sul lato proxy (tra l'applicazione client Skype for business e il Mediation Server). Poiché il Mediation Server non dispone di informazioni sul dispositivo endpoint durante la richiesta della sessione, non è possibile eseguire controlli CAC sul collegamento WAN (tra il Mediation Server e l'endpoint di terze parti) prima dello stabilimento di chiamata. Dopo che la sessione è stata stabilita, tuttavia, Mediation Server facilita la contabilità per la larghezza di banda utilizzata nel trunk.

Per le chiamate che hanno origine dall'endpoint di terze parti, le informazioni sul dispositivo endpoint sono disponibili al momento della richiesta di sessione e il controllo CAC può essere eseguito su entrambi i lati del Mediation Server.

> [!NOTE]
> Verificare che la subnet IP a cui appartengono i dispositivi endpoint sia configurata e associata a sito di rete 2.

> [!NOTE]
> Verificare che la subnet IP alla quale appartengono entrambe le interfacce del Mediation Server sia configurata e associata al sito di rete 1.

> [!NOTE]
> Per informazioni dettagliate, vedere [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).


