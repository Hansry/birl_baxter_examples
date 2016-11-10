# Overview 

This file presents the example of smach using service.
    
# Nodes

    nodes:
        services.py     --smach node as a service client
        add_two_ints_server  --a server
        add_three_ints_server  --a server
        add_four_ints_server  --a server

# Running

rosrun three server

    rosrun example_smach add_two_ints_server.py
    rosrun example_smach add_three_ints_server.py
    rosrun example_smach add_four_ints_server.py

rosrun smach viewer

    rosrun smach_viewer smach_viewer.py
    
rosrun smach node

    rosrun example_smach service.py
    
# Bug in smach_viewer

In Indigo version,your smach_viewer may fail showing 'ValueError: invalid literal for int() with base 10: '274.67''
You should rewrite the 480th row of the /opt/ros/indigo/lib/python2.7/dist-packages/xdot/xdot.py

    return int(self.read_code()) -> return int(float(self.read_code()))
    
Then it works.For detail please click the [issue](http://answers.ros.org/question/172688/ros-indigo-cannot-show-graph-view-on-smach_viewer/)
