# 备份时间索引

按备份名称中的版本时间排序，统一为 Pacific/Auckland（奥克兰时间）。
文件夹名称升序即从旧到新，降序即从新到旧。原有内容逐文件校验未改变。
同秒备份使用两位序号保持实际创建顺序。原始目录名见下表及 rename_map.json。

| 顺序 | 奥克兰时间 | 当前目录 | 原目录名 |
|---:|---|---|---|
| 1 | 2026-11-03 00:22:21 | [pre_integration](2026-11-03_00-22-21_01_pre_integration/) | `pre_integration_20261103_002221` |
| 2 | 2026-11-03 02:06:43 | [pre_expansion](2026-11-03_02-06-43_02_pre_expansion/) | `pre_expansion_20261103_020643` |
| 3 | 2026-11-03 02:12:12 | [after_expanded_iii_iv](2026-11-03_02-12-12_03_after_expanded_iii_iv/) | `after_expanded_iii_iv_20261103_021212` |
| 4 | 2026-11-03 02:15:29 | [after_background_ii_iii_iv](2026-11-03_02-15-29_04_after_background_ii_iii_iv/) | `after_background_ii_iii_iv_20261103_021529` |
| 5 | 2026-11-03 02:20:58 | [after_background_scope_review](2026-11-03_02-20-58_05_after_background_scope_review/) | `after_background_scope_review_20261103_022058` |
| 6 | 2026-11-03 04:06:28 | [pre_evaluation](2026-11-03_04-06-28_06_pre_evaluation/) | `pre_evaluation_20261103_040628` |
| 7 | 2026-11-03 04:06:28 | [after_evaluation](2026-11-03_04-06-28_07_after_evaluation/) | `after_evaluation_20261103_040628` |
| 8 | 2026-11-03 22:31:56 | [pre_latest_results](2026-11-03_22-31-56_08_pre_latest_results/) | `pre_latest_results_20261103_093156_UTC` |
| 9 | 2026-11-03 22:31:56 | [after_latest_results](2026-11-03_22-31-56_09_after_latest_results/) | `after_latest_results_20261103_093156_UTC` |
| 10 | 2026-11-03 22:35:50 | [final_latest_results](2026-11-03_22-35-50_10_final_latest_results/) | `final_latest_results_20261103_093550_UTC` |
| 11 | 2026-11-03 23:19:21 | [pre_closing_sections](2026-11-03_23-19-21_11_pre_closing_sections/) | `pre_closing_sections_20261103_101921_UTC` |
| 12 | 2026-11-03 23:19:21 | [after_closing_sections](2026-11-03_23-19-21_12_after_closing_sections/) | `after_closing_sections_20261103_101921_UTC` |
| 13 | 2026-11-03 23:20:33 | [final_closing_sections](2026-11-03_23-20-33_13_final_closing_sections/) | `final_closing_sections_20261103_102033_UTC` |
| 14 | 2026-11-04 02:44:59 | [full_before_acm_10page](2026-11-04_02-44-59_14_full_before_acm_10page/) | `full_before_acm_10page_20261103_134459_UTC` |
| 15 | 2026-11-04 03:03:52 | [acm_10page_final](2026-11-04_03-03-52_15_acm_10page_final/) | `acm_10page_final_20261103_140352_UTC` |
| 16 | 2026-11-04 11:25:04 | [before_terminology](2026-11-04_11-25-04_16_before_terminology/) | `before_terminology_20261103_222504_UTC` |
| 17 | 2026-11-04 11:33:55 | [after_terminology_sources](2026-11-04_11-33-55_17_after_terminology_sources/) | `after_terminology_sources_20261103_223355_UTC` |
| 18 | 2026-11-05 00:04:32 | [before_safety_theory_validation](2026-11-05_00-04-32_18_before_safety_theory_validation/) | 新建：安全理论验证前完整快照 |
| 19 | 2026-11-05 00:53:30 | [before_simulation_interpretation](2026-11-05_00-53-30_19_before_simulation_interpretation/) | 新建：仿真解释修订前完整快照 |

以后新增备份建议沿用 `YYYY-MM-DD_HH-mm-ss_NN_description` 格式。
历史记录中的旧路径可通过 rename_map.json 查询；已更新项目根目录内的当前进度及 provenance 文件。
