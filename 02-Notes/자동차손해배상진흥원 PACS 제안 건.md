​어제 회의 내용을 기반으로 Flow를 정리합니다.

  

  

**Use Case 1. 영상 획득**  
사건 피해자가 진단서, 소견서, 보험 관련 서류 등 피해 증빙 자료를 서비스 Portal에 업로드한다.  
Portal은 각 사건에 대해 사건번호(Unique Key)를 기준으로 자료를 관리한다.  
동시에 병원에서 수령한 CD 영상은 해당 사건번호(Key)와 함께 PACS로 전달된다.  
PACS는 전달받은 Key를 기준으로 영상을 획득(Import) 처리한다.  
획득 성공 시: 정상 저장 및 관리  
획득 실패 시: 실패 사유를 Portal로 회신  
Portal에서는 획득 실패 건에 대해 사용자가 CD Viewer 등을 통해 직접 영상을 확인할 수 있도록 안내한다.  
또한, 이후 Portal에서는 사건번호를 기준으로 PACS에 저장된 영상을 조회할 수 있다.  
  
  
**Use Case 2. 영상 조회**  
Portal에서는 피해자의 민원 처리를 위해 위원회를 구성하고 심의를 진행한다.  
위원회는 온라인/오프라인 환경에서 다수의 참여자가 함께 자료를 검토한다.  
이 과정에서 영상 확인이 필요한 경우, Portal에서 해당 사건의 영상 링크를 클릭하면 G3 Viewer 팝업을 통해 영상을 조회할 수 있다.  
이때, 하나의 사건번호에 속한 영상은 개별 단위가 아닌 사건 단위(묶음)로 한 번에 로드되어야 하며,  
위원회 참여자들은 동일한 기준의 영상 세트를 동시에 확인할 수 있어야 한다.


https://www.plantuml.com/plantuml/uml/RLDFQnD15B_lftZqb2BDnPk4K4cnY8gb9Jq9CYHZ7B8x6tTdrI92MbCf9cAX1cFSI8gXLCWXrZsqq4-KcVqElaqwmmxrjhlp-_D-lpUx7WeIYCXp7PU-421y25ZZfO0w2sXDC9yxOPFn5Wc81orIQv86tH5xBeNicF26Ins7r8GVm8ewcCx_991-lKxxYVfvl08aX5s6Afw1n1trupWTzXPd5T_pc10K9Mwa4T69vLL7VPh0bXy8ugx0EmS080ffZOGPu6mahxwZlFpL0pdx0fKDKDyEvMaiJ-A5RBNolDfoVLBF4_Luyk8e7LmMgfozYYWyedkhC4_QycoggVZf2U4uYyr6brr6tz00K4SDVuFg7yc310hfyBCy6O7gJjBUEHgiQg7DYDKjaLnyX4_LQB2OVtxHJZ-EDMkRlaQR_qqEQh2lFko3Efrb2eN7Z3UDMJPRzi5vd-jowtvb1vrYR3CzZ6yrYKbXVZbJaxQMNcOfFFHQsBtHNhxQN2lref9u33YMwfea3mXpjoa9VMvJD-_g9hLhRuGBVCOBDpbbznoB0ZMwdYSTUDgYt8f9Wopaybx1sbevjs_p1CLYsLect8DIYV6Q6zLfkUnOHvc6YOd0oeQUx0uW2jIu8xjJnp4OA1MBTa9asOrWwsX8tmhAw-XdWz7GN11aQiguB_ycnity74kukHdcIMVKgxyTqPna2gOznEL_1MsuZfD6dliF


https://www.plantuml.com/plantuml/uml/TLHVJzfG57_lfpZnIHwM_LdsGiBYmf9bsPQP6FUqbqvlbaPQ62txioTntQ9IWaIOHLk36LCUC4D5WmcVY7lkTzYvkRLfYV90Bpdd_lwSyoiBjgENdOfPqFIAKxGgvWTMrkmrmohfPTq4K__wXjcs_f4j6TyPF7poGDFq5QTOXZdS64pFHY1Q4z4UuU7E7EWsl3DM7CFKwB9Zh1WbtNAeqGtujOlRFLWibXsz81kZOxfnyLb-IHNfa2wzU4pGx0ihotfqZ8K4BXxiY7rFrY1VD4t3SHZJj5mEbcq6UTqcvLb0lue_gY3swtmtX5nEKsBXtjD83MGZDu378R_k0BdYVppWmmRmYoQHGFuvuDvFVXJmtK3o6vzrXzsOKOyKdXeIFzyK_dX-sJ8-LHYyOjyoX1bCnriIEcOvwObsCmb2Ku2if8oKOzVbjG7C9q51D0QYtS_4OjJmv5S2GztammCCroK_JCT3xArZC24hwS7ClpHB9243M0jumwLr5voe1EYUJIykDQ2F8aXPxRQLo7Ky_2kDHUs0OPFNBZLMi5aCLEi9hty7a2hAqM7GfHiUrhggLNN8vcXrsJGWO7kJRumaEOqjYWdWIHMxJH2TDePZc5vvf4zZrggsoj93I_nMLEa8FOeZX4T3aYKZ5ASjjVKuaQHhWA5F4bpnUuisv_VlezyJBPU74rAJcStGNO2AzxLXhO6eZlZnQI8daSrPTHGEl0fcq-9vnCp_ZOKxJ90h24qz4hb9tiMz7S1VTT6E0yC7LnXwmEj334S42BZVmlFJMwEOrCaR7GmdDnaC_LYuEnRRO-13NtJysUt4uWWf7XA1nVyCv2saTnDur-Fr5Z-flhSYxy1hVGnS-HRW-IXc2oVJaGjlIypA9CaKscrXMA3GLCp2Vm00