#1 support graphical-ui

   #1.1 web based -> schematic diagram

   #1.2 parameters setting of 4 levels

          Application Layer
              ↓
          Collective Layer (MockNCCL algorithms)
              ↓  
          Network Frontend (analytical/ns3/phy)
              ↓
          Physical Network (phynet)

        from implementation's view:

          #1.2.1 aicb level -> high/system level input : framework types, layer num, epoch num, ...

          #1.2.2 astra-sim level -> workload file edit

               - general characteristic : parallelization strategy, hardware resource,e.g.GPU, ...
               - 11 key fields for each layer

          #1.2.3 ccl level

               - algorithm : ring, tree, ...
               - others for nccl detemination ???

          #1.2.4 network level

               - ns-3 : congestion control
                 - rdma-sim (#2)
               - phynet : real physical device

#2 core competitveness : rdma-sim

   #2.1 enhance the rdma protocol and device simulation
          - delay
          - packet loss
          - ...

   #2.2 enhance the rdma switch simulation

   #2.3 ns-3 as base ? to easily integrate with congestion control simulation ?

#3 CCL simulation selection

   #3.1 SimAI/astra-sim-alibabacloud
          - fork from nccl and stub GPU part
            code is branched out from one version of nccl but not continuously follow nccl ?
              - nccl logic
              - topology
              - algorithm ...
          - integate with astra-sim but not accepted by astra-sim forum

   #3.2 astra-sim/astraccl
          - theoretical model
              - accurary could be a bit poor than nccl stub ?
  
   #3.3 make cclsim as one plugin of astra-sim
          - SimAI has setup SimCCL but empty
            contribute to SimCCL or genereate new cclsim ? maybe new cclsim
          - change astra-sim framework to make cclsim as plugable
            contribute the plugable framework to astra-sim is possible


