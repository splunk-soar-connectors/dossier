# Dossier for SOAR

Publisher: Splunk Community \
Connector Version: 1.2.2 \
Product Vendor: Infoblox \
Product Name: Dossier \
Minimum Product Version: 5.2.0

This app supports investigate actions on the Infoblox Dossier platform

### Configuration variables

This table lists the configuration variables required to operate Dossier for SOAR. These variables are specified when configuring a Dossier asset in Splunk SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**api_key** | required | password | API Key for Dossier Service |

### Supported Actions

[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration \
[lookup domain](#action-lookup-domain) - Check for the presence of a domain in a threat intelligence feed \
[lookup ip](#action-lookup-ip) - Check for the presence of an IP in a threat intelligence feed \
[lookup hash](#action-lookup-hash) - Check for the presence of a hash in a threat intelligence feed \
[lookup url](#action-lookup-url) - Check for the presence of a url in a threat intelligence feed

## action: 'test connectivity'

Validate the asset configuration for connectivity using supplied configuration

Type: **test** \
Read only: **True**

#### Action Parameters

No parameters are required for this action

#### Action Output

No Output

## action: 'lookup domain'

Check for the presence of a domain in a threat intelligence feed

Type: **investigate** \
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** | required | Domain to lookup | string | `domain` `url` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.domain | string | `domain` `url` | test.com |
action_result.data.\*.\*.data.record_count | numeric | | 63 |
action_result.data.\*.\*.data.threat.\*.batch_id | string | | e2960bbe-4c41-11e9-973b-118654ebd5ac |
action_result.data.\*.\*.data.threat.\*.class | string | | MalwareDownload |
action_result.data.\*.\*.data.threat.\*.confidence | numeric | | 100 |
action_result.data.\*.\*.data.threat.\*.detected | string | | 2019-03-22T01:29:05.000Z |
action_result.data.\*.\*.data.threat.\*.dga | string | | false |
action_result.data.\*.\*.data.threat.\*.domain | string | `domain` | bfmio.com |
action_result.data.\*.\*.data.threat.\*.expiration | string | | 2019-03-22T01:29:05.000Z |
action_result.data.\*.\*.data.threat.\*.extended.audience | string | | Operational |
action_result.data.\*.\*.data.threat.\*.extended.etcategory | string | | Known Trojan Command and Control Server |
action_result.data.\*.\*.data.threat.\*.extended.hash_md5 | string | `md5` | ec60ed09055a95f13a233f4432d3b009 |
action_result.data.\*.\*.data.threat.\*.extended.hash_sha1 | string | `sha1` | 1bd2613fb883849289b4f88c6ce4f4b6c10a0d76 |
action_result.data.\*.\*.data.threat.\*.extended.hash_sha256 | string | `sha256` | 719852ff3fd6e1aadfb05cd08a43e3aae2ddbb20d77cb90892b711d732e46867 |
action_result.data.\*.\*.data.threat.\*.extended.intelligencetype | string | | malware |
action_result.data.\*.\*.data.threat.\*.extended.killchain | string | | C2 |
action_result.data.\*.\*.data.threat.\*.extended.maliciousconfidence | string | | High |
action_result.data.\*.\*.data.threat.\*.extended.malware | string | | Azorult |
action_result.data.\*.\*.data.threat.\*.extended.malwarefamily | string | | arbceezrer |
action_result.data.\*.\*.data.threat.\*.extended.networkidentifier | string | | Attacker |
action_result.data.\*.\*.data.threat.\*.extended.networktype | string | | network |
action_result.data.\*.\*.data.threat.\*.extended.observationtime | string | | 1568170260 |
action_result.data.\*.\*.data.threat.\*.extended.ports | string | | 80 |
action_result.data.\*.\*.data.threat.\*.extended.reportid | string | | 19-00015343 |
action_result.data.\*.\*.data.threat.\*.extended.threatscape | string | | Cyber Crime |
action_result.data.\*.\*.data.threat.\*.extended.threattype | string | | InformationStealer |
action_result.data.\*.\*.data.threat.\*.extended.title | string | | Indicator Report: arbceezrer Activity Report (Sep 10, 2019) |
action_result.data.\*.\*.data.threat.\*.extended.url_hash | string | `md5` | ed6e3ced1896c6808b02baaf7dbba1e2 |
action_result.data.\*.\*.data.threat.\*.host | string | | test.com |
action_result.data.\*.\*.data.threat.\*.id | string | | e2b5a1e3-4c41-11e9-973b-118654ebd5ac |
action_result.data.\*.\*.data.threat.\*.imported | string | | 2019-03-22T01:29:06.978Z |
action_result.data.\*.\*.data.threat.\*.ip | string | `ip` | 1.1.1.1 |
action_result.data.\*.\*.data.threat.\*.origin | string | | |
action_result.data.\*.\*.data.threat.\*.profile | string | | CrowdStrike |
action_result.data.\*.\*.data.threat.\*.property | string | | MalwareDownload_Generic |
action_result.data.\*.\*.data.threat.\*.received | string | | 2019-03-22T01:29:06.978Z |
action_result.data.\*.\*.data.threat.\*.target | string | | |
action_result.data.\*.\*.data.threat.\*.threat_level | numeric | | 100 |
action_result.data.\*.\*.data.threat.\*.tld | string | | cn com |
action_result.data.\*.\*.data.threat.\*.tlp | string | | |
action_result.data.\*.\*.data.threat.\*.type | string | | HOST |
action_result.data.\*.\*.data.threat.\*.up | string | | true |
action_result.data.\*.\*.data.threat.\*.url | string | `url` | |
action_result.data.\*.\*.params.source | string | | atp |
action_result.data.\*.\*.params.target | string | | test.com |
action_result.data.\*.\*.params.type | string | | host |
action_result.data.\*.\*.status | string | | success |
action_result.data.\*.\*.task_id | string | | d63861e8-a0de-429f-8185-09ecacda38b5 |
action_result.data.\*.\*.time | numeric | | 127 |
action_result.data.\*.\*.v | string | | 3.0.0 |
action_result.status | string | | success failed |
action_result.message | string | | Threat confidence: 70, Threat level: 70 |
action_result.summary.threat_confidence | numeric | | 70 |
action_result.summary.threat_level | numeric | | 70 |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'lookup ip'

Check for the presence of an IP in a threat intelligence feed

Type: **investigate** \
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** | required | IP to lookup | string | `ip` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.ip | string | `ip` | 1.1.1.1 |
action_result.data.\*.\*.data.record_count | numeric | | 71 |
action_result.data.\*.\*.data.threat.\*.batch_id | string | | 5161b3b9-decd-11e9-ba13-8bf13d8099cf |
action_result.data.\*.\*.data.threat.\*.class | string | | MalwareC2 |
action_result.data.\*.\*.data.threat.\*.confidence | numeric | | 97 |
action_result.data.\*.\*.data.threat.\*.confidence_score | numeric | | 0.1 |
action_result.data.\*.\*.data.threat.\*.confidence_score_rating | string | | Unconfirmed |
action_result.data.\*.\*.data.threat.\*.confidence_score_vector | string | | COSIS:1.0/SR:N/POP:N/TLD:N/CP:T |
action_result.data.\*.\*.data.threat.\*.detected | string | | 2019-09-18T00:00:00.000Z |
action_result.data.\*.\*.data.threat.\*.domain | string | `domain` | |
action_result.data.\*.\*.data.threat.\*.expiration | string | | 2019-09-30T17:07:58.000Z |
action_result.data.\*.\*.data.threat.\*.extended.cyberint_guid | string | `md5` | adfb82a2bedfb544dacc544a99a529b6 |
action_result.data.\*.\*.data.threat.\*.extended.etcategory | string | | Known Trojan Command and Control Server |
action_result.data.\*.\*.data.threat.\*.extended.ports | string | | 447 |
action_result.data.\*.\*.data.threat.\*.host | string | | |
action_result.data.\*.\*.data.threat.\*.id | string | | 567a2ce4-decd-11e9-ba13-8bf13d8099cf |
action_result.data.\*.\*.data.threat.\*.imported | string | | 2019-09-24T13:15:03.346Z |
action_result.data.\*.\*.data.threat.\*.ip | string | `ip` | 1.1.1.1 |
action_result.data.\*.\*.data.threat.\*.origin | string | | |
action_result.data.\*.\*.data.threat.\*.profile | string | | EmergingThreats |
action_result.data.\*.\*.data.threat.\*.property | string | | MalwareC2_Generic |
action_result.data.\*.\*.data.threat.\*.received | string | | 2019-09-24T13:15:03.346Z |
action_result.data.\*.\*.data.threat.\*.target | string | | |
action_result.data.\*.\*.data.threat.\*.threat_level | numeric | | 0 |
action_result.data.\*.\*.data.threat.\*.tld | string | | |
action_result.data.\*.\*.data.threat.\*.tlp | string | | |
action_result.data.\*.\*.data.threat.\*.type | string | | IP |
action_result.data.\*.\*.data.threat.\*.up | string | | true |
action_result.data.\*.\*.data.threat.\*.url | string | `url` | |
action_result.data.\*.\*.params.source | string | | atp |
action_result.data.\*.\*.params.target | string | `ip` | 1.1.1.1 |
action_result.data.\*.\*.params.type | string | | ip |
action_result.data.\*.\*.status | string | | success |
action_result.data.\*.\*.task_id | string | | e8fc5f0d-ba41-4d34-ad87-5a9a596e7787 |
action_result.data.\*.\*.time | numeric | | 58 |
action_result.data.\*.\*.v | string | | 3.0.0 |
action_result.status | string | | success failed |
action_result.message | string | | Results: 71 |
action_result.summary.results | numeric | | 71 |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'lookup hash'

Check for the presence of a hash in a threat intelligence feed

Type: **investigate** \
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** | required | Hash to lookup | string | `sha256` `sha1` `md5` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.hash | string | `sha256` `sha1` `md5` | abafd238c79d76955e6464f0e85acb33 |
action_result.data.\*.\*.data.details.av_engine_count | numeric | | 72 |
action_result.data.\*.\*.data.details.av_match_count | numeric | | 60 |
action_result.data.\*.\*.data.details.av_scan_time | string | | |
action_result.data.\*.\*.data.details.av_scans.ALYac.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.ALYac.result | string | | Dropped:Generic.Malware.Fdld.85679D2E |
action_result.data.\*.\*.data.details.av_scans.ALYac.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.ALYac.version | string | `ip` | 1.1.1.5 |
action_result.data.\*.\*.data.details.av_scans.APEX.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.APEX.result | string | | Malicious |
action_result.data.\*.\*.data.details.av_scans.APEX.update_time | string | | 20190713 |
action_result.data.\*.\*.data.details.av_scans.APEX.version | string | | 5.38 |
action_result.data.\*.\*.data.details.av_scans.AVG.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.AVG.result | string | | Win32:Nitol-B [Trj] |
action_result.data.\*.\*.data.details.av_scans.AVG.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.AVG.version | string | | 18.4.3895.0 |
action_result.data.\*.\*.data.details.av_scans.Acronis.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Acronis.result | string | | suspicious |
action_result.data.\*.\*.data.details.av_scans.Acronis.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.Acronis.version | string | `ip` | 1.0.1.51 |
action_result.data.\*.\*.data.details.av_scans.Ad-Aware.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Ad-Aware.result | string | | Dropped:Generic.Malware.Fdld.85679D2E |
action_result.data.\*.\*.data.details.av_scans.Ad-Aware.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Ad-Aware.version | string | | 3.0.5.370 |
action_result.data.\*.\*.data.details.av_scans.AegisLab.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.AegisLab.result | string | | Trojan.Win32.Generic.m2Bz |
action_result.data.\*.\*.data.details.av_scans.AegisLab.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.AegisLab.version | string | | 4.2 |
action_result.data.\*.\*.data.details.av_scans.AhnLab-V3.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.AhnLab-V3.result | string | | Trojan/Win32.Nitol.R201779 |
action_result.data.\*.\*.data.details.av_scans.AhnLab-V3.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.AhnLab-V3.version | string | | 3.15.3.24531 |
action_result.data.\*.\*.data.details.av_scans.Alibaba.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Alibaba.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Alibaba.update_time | string | | 20190527 |
action_result.data.\*.\*.data.details.av_scans.Alibaba.version | string | `ip` | 0.3.0.5 |
action_result.data.\*.\*.data.details.av_scans.Antiy-AVL.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Antiy-AVL.result | string | | Trojan/Win32.AGeneric |
action_result.data.\*.\*.data.details.av_scans.Antiy-AVL.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Antiy-AVL.version | string | `ip` | 3.0.0.1 |
action_result.data.\*.\*.data.details.av_scans.Arcabit.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Arcabit.result | string | | Generic.Malware.Fdld.85679D2E |
action_result.data.\*.\*.data.details.av_scans.Arcabit.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.Arcabit.version | string | | 1.0.0.850 |
action_result.data.\*.\*.data.details.av_scans.Avast-Mobile.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Avast-Mobile.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Avast-Mobile.update_time | string | | 20190713 |
action_result.data.\*.\*.data.details.av_scans.Avast-Mobile.version | string | | 190713-00 |
action_result.data.\*.\*.data.details.av_scans.Avast.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Avast.result | string | | Win32:Nitol-B [Trj] |
action_result.data.\*.\*.data.details.av_scans.Avast.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Avast.version | string | | 18.4.3895.0 |
action_result.data.\*.\*.data.details.av_scans.Avira.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Avira.result | string | | TR/Dropper.Gen |
action_result.data.\*.\*.data.details.av_scans.Avira.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Avira.version | string | `ip` | 8.3.3.8 |
action_result.data.\*.\*.data.details.av_scans.Baidu.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Baidu.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Baidu.update_time | string | | 20190318 |
action_result.data.\*.\*.data.details.av_scans.Baidu.version | string | `ip` | 1.0.0.2 |
action_result.data.\*.\*.data.details.av_scans.BitDefender.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.BitDefender.result | string | | Dropped:Generic.Malware.Fdld.85679D2E |
action_result.data.\*.\*.data.details.av_scans.BitDefender.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.BitDefender.version | string | | 7.2 |
action_result.data.\*.\*.data.details.av_scans.Bkav.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Bkav.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Bkav.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.Bkav.version | string | | 1.3.0.10239 |
action_result.data.\*.\*.data.details.av_scans.CAT-QuickHeal.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.CAT-QuickHeal.result | string | | Trojan.Nitol.A |
action_result.data.\*.\*.data.details.av_scans.CAT-QuickHeal.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.CAT-QuickHeal.version | string | | 14.00 |
action_result.data.\*.\*.data.details.av_scans.CMC.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.CMC.result | string | | |
action_result.data.\*.\*.data.details.av_scans.CMC.update_time | string | | 20190321 |
action_result.data.\*.\*.data.details.av_scans.CMC.version | string | | 1.1.0.977 |
action_result.data.\*.\*.data.details.av_scans.ClamAV.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.ClamAV.result | string | | Win.Trojan.Nitol-6335025-0 |
action_result.data.\*.\*.data.details.av_scans.ClamAV.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.ClamAV.version | string | `ip` | 0.101.2.0 |
action_result.data.\*.\*.data.details.av_scans.Comodo.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Comodo.result | string | | TrojWare.Win32.GameThief.Magania.~NWABI@1775fs |
action_result.data.\*.\*.data.details.av_scans.Comodo.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Comodo.version | string | | 31167 |
action_result.data.\*.\*.data.details.av_scans.CrowdStrike.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.CrowdStrike.result | string | | win/malicious_confidence_100% (D) |
action_result.data.\*.\*.data.details.av_scans.CrowdStrike.update_time | string | | 20190212 |
action_result.data.\*.\*.data.details.av_scans.CrowdStrike.version | string | | 1.0 |
action_result.data.\*.\*.data.details.av_scans.Cybereason.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Cybereason.result | string | | malicious.8c79d7 |
action_result.data.\*.\*.data.details.av_scans.Cybereason.update_time | string | | 20190616 |
action_result.data.\*.\*.data.details.av_scans.Cybereason.version | string | | 1.2.449 |
action_result.data.\*.\*.data.details.av_scans.Cylance.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Cylance.result | string | | Unsafe |
action_result.data.\*.\*.data.details.av_scans.Cylance.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Cylance.version | string | `ip` | 2.3.1.101 |
action_result.data.\*.\*.data.details.av_scans.Cyren.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Cyren.result | string | | W32/S-a7b53705!Eldorado |
action_result.data.\*.\*.data.details.av_scans.Cyren.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Cyren.version | string | `ip` | 6.2.0.1 |
action_result.data.\*.\*.data.details.av_scans.DrWeb.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.DrWeb.result | string | | Trojan.DownLoader24.51669 |
action_result.data.\*.\*.data.details.av_scans.DrWeb.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.DrWeb.version | string | | 7.0.34.11020 |
action_result.data.\*.\*.data.details.av_scans.ESET-NOD32.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.ESET-NOD32.result | string | | a variant of Win32/ServStart.IK |
action_result.data.\*.\*.data.details.av_scans.ESET-NOD32.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.ESET-NOD32.version | string | | 19683 |
action_result.data.\*.\*.data.details.av_scans.Emsisoft.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Emsisoft.result | string | | Dropped:Generic.Malware.Fdld.85679D2E (B) |
action_result.data.\*.\*.data.details.av_scans.Emsisoft.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Emsisoft.version | string | | 2018.12.0.1641 |
action_result.data.\*.\*.data.details.av_scans.Endgame.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Endgame.result | string | | malicious (high confidence) |
action_result.data.\*.\*.data.details.av_scans.Endgame.update_time | string | | 20190522 |
action_result.data.\*.\*.data.details.av_scans.Endgame.version | string | | 3.0.12 |
action_result.data.\*.\*.data.details.av_scans.F-Prot.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.F-Prot.result | string | | W32/S-a7b53705!Eldorado |
action_result.data.\*.\*.data.details.av_scans.F-Prot.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.F-Prot.version | string | `ip` | 4.7.1.166 |
action_result.data.\*.\*.data.details.av_scans.F-Secure.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.F-Secure.result | string | | Trojan.TR/Dropper.Gen |
action_result.data.\*.\*.data.details.av_scans.F-Secure.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.F-Secure.version | string | `ip` | 12.0.86.52 |
action_result.data.\*.\*.data.details.av_scans.FireEye.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.FireEye.result | string | | Generic.mg.abafd238c79d7695 |
action_result.data.\*.\*.data.details.av_scans.FireEye.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.FireEye.version | string | `ip` | 29.7.0.0 |
action_result.data.\*.\*.data.details.av_scans.Fortinet.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Fortinet.result | string | | W32/Generic.AC.2D85!tr |
action_result.data.\*.\*.data.details.av_scans.Fortinet.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Fortinet.version | string | `ip` | 5.4.247.0 |
action_result.data.\*.\*.data.details.av_scans.GData.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.GData.result | string | | Dropped:Generic.Malware.Fdld.85679D2E |
action_result.data.\*.\*.data.details.av_scans.GData.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.GData.version | string | | A:25.22720B:25.15548 |
action_result.data.\*.\*.data.details.av_scans.Ikarus.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Ikarus.result | string | | Trojan.Win32.Agent |
action_result.data.\*.\*.data.details.av_scans.Ikarus.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Ikarus.version | string | `ip` | 0.1.5.2 |
action_result.data.\*.\*.data.details.av_scans.Invincea.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Invincea.result | string | | heuristic |
action_result.data.\*.\*.data.details.av_scans.Invincea.update_time | string | | 20190525 |
action_result.data.\*.\*.data.details.av_scans.Invincea.version | string | | 6.3.6.26157 |
action_result.data.\*.\*.data.details.av_scans.Jiangmin.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Jiangmin.result | string | | Trojan.Generic.brsmj |
action_result.data.\*.\*.data.details.av_scans.Jiangmin.update_time | string | | 20190713 |
action_result.data.\*.\*.data.details.av_scans.Jiangmin.version | string | | 16.0.100 |
action_result.data.\*.\*.data.details.av_scans.K7AntiVirus.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.K7AntiVirus.result | string | | Trojan ( 0054d1101 ) |
action_result.data.\*.\*.data.details.av_scans.K7AntiVirus.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.K7AntiVirus.version | string | | 11.56.31472 |
action_result.data.\*.\*.data.details.av_scans.K7GW.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.K7GW.result | string | | Trojan ( 0054d1101 ) |
action_result.data.\*.\*.data.details.av_scans.K7GW.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.K7GW.version | string | | 11.56.31472 |
action_result.data.\*.\*.data.details.av_scans.Kaspersky.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Kaspersky.result | string | | HEUR:Trojan.Win32.Generic |
action_result.data.\*.\*.data.details.av_scans.Kaspersky.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Kaspersky.version | string | `ip` | 15.0.1.13 |
action_result.data.\*.\*.data.details.av_scans.Kingsoft.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Kingsoft.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Kingsoft.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Kingsoft.version | string | | 2013.8.14.323 |
action_result.data.\*.\*.data.details.av_scans.MAX.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.MAX.result | string | | malware (ai score=89) |
action_result.data.\*.\*.data.details.av_scans.MAX.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.MAX.version | string | | 2018.9.12.1 |
action_result.data.\*.\*.data.details.av_scans.Malwarebytes.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Malwarebytes.result | string | | Trojan.ServStart |
action_result.data.\*.\*.data.details.av_scans.Malwarebytes.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Malwarebytes.version | string | | 2.1.1.1115 |
action_result.data.\*.\*.data.details.av_scans.MaxSecure.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.MaxSecure.result | string | | Trojan.Win32.Nitol.B |
action_result.data.\*.\*.data.details.av_scans.MaxSecure.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.MaxSecure.version | string | `ip` | 1.0.0.1 |
action_result.data.\*.\*.data.details.av_scans.McAfee-GW-Edition.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.McAfee-GW-Edition.result | string | | BehavesLike.Win32.Generic.qh |
action_result.data.\*.\*.data.details.av_scans.McAfee-GW-Edition.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.McAfee-GW-Edition.version | string | | v2017.3010 |
action_result.data.\*.\*.data.details.av_scans.McAfee.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.McAfee.result | string | | GenericRXBM-KE!ABAFD238C79D |
action_result.data.\*.\*.data.details.av_scans.McAfee.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.McAfee.version | string | | 6.0.6.653 |
action_result.data.\*.\*.data.details.av_scans.MicroWorld-eScan.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.MicroWorld-eScan.result | string | | Dropped:Generic.Malware.Fdld.85679D2E |
action_result.data.\*.\*.data.details.av_scans.MicroWorld-eScan.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.MicroWorld-eScan.version | string | | 14.0.297.0 |
action_result.data.\*.\*.data.details.av_scans.Microsoft.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Microsoft.result | string | | DDoS:Win32/Nitol.A |
action_result.data.\*.\*.data.details.av_scans.Microsoft.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Microsoft.version | string | | 1.1.16100.4 |
action_result.data.\*.\*.data.details.av_scans.NANO-Antivirus.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.NANO-Antivirus.result | string | | Trojan.Win32.ServStart.epnptq |
action_result.data.\*.\*.data.details.av_scans.NANO-Antivirus.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.NANO-Antivirus.version | string | | 1.0.134.24849 |
action_result.data.\*.\*.data.details.av_scans.Paloalto.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Paloalto.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Paloalto.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Paloalto.version | string | | 1.0 |
action_result.data.\*.\*.data.details.av_scans.Panda.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Panda.result | string | | Trj/Genetic.gen |
action_result.data.\*.\*.data.details.av_scans.Panda.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Panda.version | string | `ip` | 4.6.4.2 |
action_result.data.\*.\*.data.details.av_scans.Qihoo-360.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Qihoo-360.result | string | | HEUR/QVM07.1.8477.Malware.Gen |
action_result.data.\*.\*.data.details.av_scans.Qihoo-360.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Qihoo-360.version | string | | 1.0.0.1120 |
action_result.data.\*.\*.data.details.av_scans.Rising.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Rising.result | string | | Backdoor.Overie!1.64BD (CLASSIC) |
action_result.data.\*.\*.data.details.av_scans.Rising.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Rising.version | string | `ip` | 25.0.0.24 |
action_result.data.\*.\*.data.details.av_scans.SUPERAntiSpyware.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.SUPERAntiSpyware.result | string | | Trojan.Agent/Gen-ServStart |
action_result.data.\*.\*.data.details.av_scans.SUPERAntiSpyware.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.SUPERAntiSpyware.version | string | | 5.6.0.1032 |
action_result.data.\*.\*.data.details.av_scans.SentinelOne.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.SentinelOne.result | string | | DFI - Malicious PE |
action_result.data.\*.\*.data.details.av_scans.SentinelOne.update_time | string | | 20190604 |
action_result.data.\*.\*.data.details.av_scans.SentinelOne.version | string | | 1.0.27.333 |
action_result.data.\*.\*.data.details.av_scans.Sophos.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Sophos.result | string | | Troj/Agent-AYVZ |
action_result.data.\*.\*.data.details.av_scans.Sophos.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Sophos.version | string | | 4.98.0 |
action_result.data.\*.\*.data.details.av_scans.Symantec.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Symantec.result | string | | Trojan.Gen.MBT |
action_result.data.\*.\*.data.details.av_scans.Symantec.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Symantec.version | string | `ip` | 1.9.0.0 |
action_result.data.\*.\*.data.details.av_scans.TACHYON.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.TACHYON.result | string | | |
action_result.data.\*.\*.data.details.av_scans.TACHYON.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.TACHYON.version | string | | 2019-07-14.02 |
action_result.data.\*.\*.data.details.av_scans.Tencent.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Tencent.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Tencent.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Tencent.version | string | `ip` | 1.0.0.1 |
action_result.data.\*.\*.data.details.av_scans.TotalDefense.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.TotalDefense.result | string | | |
action_result.data.\*.\*.data.details.av_scans.TotalDefense.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.TotalDefense.version | string | `ip` | 37.1.62.1 |
action_result.data.\*.\*.data.details.av_scans.Trapmine.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Trapmine.result | string | | malicious.high.ml.score |
action_result.data.\*.\*.data.details.av_scans.Trapmine.update_time | string | | 20190522 |
action_result.data.\*.\*.data.details.av_scans.Trapmine.version | string | | 3.1.62.789 |
action_result.data.\*.\*.data.details.av_scans.TrendMicro-HouseCall.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.TrendMicro-HouseCall.result | string | | DDOS_NITOL.SMC |
action_result.data.\*.\*.data.details.av_scans.TrendMicro-HouseCall.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.TrendMicro-HouseCall.version | string | | 10.0.0.1040 |
action_result.data.\*.\*.data.details.av_scans.TrendMicro.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.TrendMicro.result | string | | DDOS_NITOL.SMC |
action_result.data.\*.\*.data.details.av_scans.TrendMicro.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.TrendMicro.version | string | | 11.0.0.1006 |
action_result.data.\*.\*.data.details.av_scans.Trustlook.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Trustlook.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Trustlook.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Trustlook.version | string | | 1.0 |
action_result.data.\*.\*.data.details.av_scans.VBA32.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.VBA32.result | string | | Trojan.Downloader |
action_result.data.\*.\*.data.details.av_scans.VBA32.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.VBA32.version | string | | 4.0.0 |
action_result.data.\*.\*.data.details.av_scans.VIPRE.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.VIPRE.result | string | | Trojan.Win32.Nitol.b (v) |
action_result.data.\*.\*.data.details.av_scans.VIPRE.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.VIPRE.version | string | | 76414 |
action_result.data.\*.\*.data.details.av_scans.ViRobot.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.ViRobot.result | string | | Dropper.Agent.54110 |
action_result.data.\*.\*.data.details.av_scans.ViRobot.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.ViRobot.version | string | | 2014.3.20.0 |
action_result.data.\*.\*.data.details.av_scans.Webroot.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Webroot.result | string | | W32.Trojan.Gen |
action_result.data.\*.\*.data.details.av_scans.Webroot.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.Webroot.version | string | | 1.0.0.403 |
action_result.data.\*.\*.data.details.av_scans.Yandex.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Yandex.result | string | | Trojan.Agent!bGserAaTiB0 |
action_result.data.\*.\*.data.details.av_scans.Yandex.update_time | string | | 20190711 |
action_result.data.\*.\*.data.details.av_scans.Yandex.version | string | `ip` | 5.5.2.24 |
action_result.data.\*.\*.data.details.av_scans.Zillya.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Zillya.result | string | | Trojan.ServStart.Win32.16461 |
action_result.data.\*.\*.data.details.av_scans.Zillya.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.Zillya.version | string | | 2.0.0.3852 |
action_result.data.\*.\*.data.details.av_scans.ZoneAlarm.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.ZoneAlarm.result | string | | HEUR:Trojan.Win32.Generic |
action_result.data.\*.\*.data.details.av_scans.ZoneAlarm.update_time | string | | 20190713 |
action_result.data.\*.\*.data.details.av_scans.ZoneAlarm.version | string | | 1.0 |
action_result.data.\*.\*.data.details.av_scans.Zoner.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.Zoner.result | string | | |
action_result.data.\*.\*.data.details.av_scans.Zoner.update_time | string | | 20190712 |
action_result.data.\*.\*.data.details.av_scans.Zoner.version | string | | 1.0 |
action_result.data.\*.\*.data.details.av_scans.eGambit.detected | boolean | | True False |
action_result.data.\*.\*.data.details.av_scans.eGambit.result | string | | Trojan.Generic |
action_result.data.\*.\*.data.details.av_scans.eGambit.update_time | string | | 20190714 |
action_result.data.\*.\*.data.details.av_scans.eGambit.version | string | | v4.3.6 |
action_result.data.\*.\*.data.details.md5 | string | `md5` | abafd238c79d76955e6464f0e85acb33 |
action_result.data.\*.\*.data.details.sha1 | string | `sha1` | 2f3c70d614571d8decba26b9a42a719662bc4647 |
action_result.data.\*.\*.data.details.sha256 | string | `sha256` | dbd83f1eb252150339f8fd86cdb86d7113bcc3e5fdabcabf831d8c6a02c4a5d1 |
action_result.data.\*.\*.data.match | boolean | | True False |
action_result.data.\*.\*.data.summary.av_engine_count | numeric | | 72 |
action_result.data.\*.\*.data.summary.av_match_count | numeric | | 60 |
action_result.data.\*.\*.data.summary.av_match_percent | numeric | | 0.8333333333333334 |
action_result.data.\*.\*.data.summary.first_seen | string | | 2019-07-14 11:47:40 |
action_result.data.\*.\*.data.summary.last_seen | string | | 2019-07-14 11:47:40 |
action_result.data.\*.\*.data.summary.status | string | | MALICIOUS |
action_result.data.\*.\*.data.summary.threat_level | numeric | | 1 |
action_result.data.\*.\*.data.summary.trust_factor | numeric | | 0 |
action_result.data.\*.\*.params.source | string | | gcs |
action_result.data.\*.\*.params.target | string | `md5` | abafd238c79d76955e6464f0e85acb33 |
action_result.data.\*.\*.params.type | string | | hash |
action_result.data.\*.\*.status | string | | success |
action_result.data.\*.\*.task_id | string | | 2d7028a6-0d99-4d85-86bb-95b89042b3cb |
action_result.data.\*.\*.time | numeric | | 259 |
action_result.data.\*.\*.v | string | | 3.0.0 |
action_result.status | string | | success failed |
action_result.message | string | | |
action_result.summary | string | | |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'lookup url'

Check for the presence of a url in a threat intelligence feed

Type: **investigate** \
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** | required | URL to lookup | string | `url` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.url | string | `url` | https://appleid.iosots.cn/id |
action_result.data.\*.\*.data.record_count | numeric | | 1 |
action_result.data.\*.\*.data.threat.\*.batch_id | string | | a6c230db-de13-11e9-a73a-7f7cc7d8bfc3 |
action_result.data.\*.\*.data.threat.\*.class | string | | Phishing |
action_result.data.\*.\*.data.threat.\*.confidence_score | numeric | | 7.7 |
action_result.data.\*.\*.data.threat.\*.confidence_score_rating | string | | High |
action_result.data.\*.\*.data.threat.\*.confidence_score_vector | string | | COSIS:1.0/SR:H/POP:N/TLD:N/CP:F |
action_result.data.\*.\*.data.threat.\*.detected | string | | 2019-09-23T15:05:27.791Z |
action_result.data.\*.\*.data.threat.\*.domain | string | `domain` | iosots.cn |
action_result.data.\*.\*.data.threat.\*.expiration | string | | 2019-10-07T15:05:27.791Z |
action_result.data.\*.\*.data.threat.\*.extended.cyberint_guid | string | `md5` | b445a69bee614141e8f2e16dc73f14bd |
action_result.data.\*.\*.data.threat.\*.extended.protocol | string | `url` | https |
action_result.data.\*.\*.data.threat.\*.extended.url_hash | string | `md5` | 1d9d85864013730fb6fd5b23a2057f8d |
action_result.data.\*.\*.data.threat.\*.host | string | | appleid.iosots.cn |
action_result.data.\*.\*.data.threat.\*.id | string | | a6c4a1de-de13-11e9-a73a-7f7cc7d8bfc3 |
action_result.data.\*.\*.data.threat.\*.imported | string | | 2019-09-23T15:05:59.503Z |
action_result.data.\*.\*.data.threat.\*.ip | string | `ip` | 1.1.1.1 |
action_result.data.\*.\*.data.threat.\*.origin | string | | |
action_result.data.\*.\*.data.threat.\*.profile | string | | IID |
action_result.data.\*.\*.data.threat.\*.property | string | | Phishing_Generic |
action_result.data.\*.\*.data.threat.\*.received | string | | 2019-09-23T15:05:59.503Z |
action_result.data.\*.\*.data.threat.\*.risk_score | numeric | | 7.9 |
action_result.data.\*.\*.data.threat.\*.risk_score_rating | string | | High |
action_result.data.\*.\*.data.threat.\*.risk_score_vector | string | | RSIS:1.0/TSS:M/TLD:N/CVSS:L/EX:H/MOD:N/AVL:N/T:M/DT:L |
action_result.data.\*.\*.data.threat.\*.target | string | | |
action_result.data.\*.\*.data.threat.\*.threat_level | numeric | | 100 |
action_result.data.\*.\*.data.threat.\*.threat_score | numeric | | 5.8 |
action_result.data.\*.\*.data.threat.\*.threat_score_rating | string | | Medium |
action_result.data.\*.\*.data.threat.\*.threat_score_vector | string | | TSIS:1.0/AV:N/AC:L/PR:L/UI:R/EX:H/MOD:N/AVL:N/CI:N/ASN:N/TLD:N/DOP:N/P:F |
action_result.data.\*.\*.data.threat.\*.tld | string | | cn |
action_result.data.\*.\*.data.threat.\*.tlp | string | | |
action_result.data.\*.\*.data.threat.\*.type | string | | URL |
action_result.data.\*.\*.data.threat.\*.up | string | | true |
action_result.data.\*.\*.data.threat.\*.url | string | `url` | https://appleid.iosots.cn/id |
action_result.data.\*.\*.params.source | string | | atp |
action_result.data.\*.\*.params.target | string | `url` | https://appleid.iosots.cn/id |
action_result.data.\*.\*.params.type | string | | url |
action_result.data.\*.\*.status | string | | success |
action_result.data.\*.\*.task_id | string | | 58713b2a-2cce-4f3a-bfe0-5f8f3dfb60fe |
action_result.data.\*.\*.time | numeric | | 53 |
action_result.data.\*.\*.v | string | | 3.0.0 |
action_result.status | string | | success failed |
action_result.message | string | | |
action_result.summary | string | | |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

______________________________________________________________________

Auto-generated Splunk SOAR Connector documentation.

Copyright 2025 Splunk Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
