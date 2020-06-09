# Benchmarking {#part:benchmarking level=part status=ready}

Author: Linus Lingg

Maintainer: Linus Lingg

This section of the book focuses on the concept of behaviour benchmarking in Duckietown.

Below you can see the general architecture that was set up for the Behaviour Benchmarking.

![Architecture](/media/Architecture.png){ width=80% }

So first of all the Behaviour defines the experiment definition as well as the environment definition. Based on that the hardware set up is explained and can be done. After this there will be a Hardware check which assures that everything is ready to do a fair Benchmark.
Furthermore, the software preparation can be done.
After this all is ready to run the actual experiments in which all the needed data is recorded. It is necessary to run at least two experiments. This means, on one hand the diagnostic toolbox is running to record all kind of information about CPU usage, memory usage etc., on the other hand a bag is recorded directly on the Duckiebot which records all kind of necessary data published directly by the Duckiebot on one hand to record its estimation and on the other hand to be able to check the latency as well as the update frequency of the nodes etc. And last but not least a bag is recorded that records everything from the localization system which is the Ground Truth (same procedure as offline localization). The localization system measures the position of the center of the April Tag placed on top of the localization standoff on the Duckiebot.
So each time I talk about the position of the Duckiebot or the speed (for example time needed per tile etc) I talk about the center of the AprilTag on top of the Duckiebot. This means that these results require that this April Tag has been mounted very precisely
The recorded bags are then processed:
The one recorded on the Duckiebot to extract the Information about latency, update frequency of the nodes as well as the needed information published by the Duckiebot and saves it into json files. The one from the localization system is processed as explained in the classical offline localization system to extract the ground truth information about the whereabouts of the Duckiebot. The original post-processor just processes the apriltags and odometry from the bag and writes it in a processed bag. I did modify this one a little bit to extract the relative pose estimation of the Duckiebot  and write it directly in a .yaml file. The graph-optimizer then will extract the ground truth trajectories of all the Duckiebots that were in sight and store it in a yaml file.
The processed data is then analyzed in different notebooks. In these notebooks it is analyzed if the measurements are stable enough such they can be actually compared to other results. If the standard deviation is too high the user is told to run another experiment to collect more data. As soon as the standard deviation is low enough the mean of the measurements is calculated and then stored into yaml file that then can be compared to other results.
In the very end a final report can be extracted which summarizes the entire Benchmark.


So let me specify a couple of things:
The environment definition includes the map design, the number of Duckiebots needed to run this Benchmark, as well as the light condition.
The experiment definition includes information about how to run the experiment in which all the data is collected. So where to place the Duckiebots involved, what to do, when the Benchmark is terminated etc. is defined there. Also, the metrics used to actually score the behaviour is defined.
Last but not least the repetition criteria is defined. This means it is defined, which data we look at to check if the results are kind of stable and therefor reliable. This is to sort out lucky runs for example.

The Software preparation: As this Behaviour Benchmarking is there to actually test the software , most of this is depending on which SW the user wants to test. However, it also includes the preparation of the localization system etc. To test a specific component/packages of dt-core, there is a prepared repository to  simply add your modified package and build/run it within a specific version of dt-core. This works for all kind of distribution of dt-core that can be used in lane_following and/or indefinite navigation.
Also in this package, one can lighten the launch file a bit in case the contribution is not very stable.

The Hardware Check: is a python script that runs the user through a couple of questions and verifies that all is done in a correct fashion and all is prepared to be later fairly compared to other results.
The result of the HW check you can see here, the verdict means that all of the questions that the user is asked have been answered with true. All the other information is pretty self explanatory.


To design a Behaviour Benchmark in the future, all the needed packages can be found in [this repository](https://github.com/llingg/behaviour-benchmarking), simply (fork and) clone it and run the different packages.
Within the readme file of this repository it is all explained on how to proceed to set up a Benchmark.

<minitoc/>
