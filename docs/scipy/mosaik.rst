========================================
Mosaik
========================================
.. highlight:: bash

mosaik is a simulator manager!

resource
-----------
* https://mosaik.offis.de
* http://mosaik.readthedocs.io/en/latest/index.html

installation
------------------------
mosaik::

  $ cd mosaik
  $ pyenv virtualenv 3.5.0 mosaik35
  $ pyenv local mosaik35
  $ pip install mosaik

mosaik-demo::

  $ brew install hg gcc hdf5
  $ pip install numpy scipy h5py
  $ hg clone https://bitbucket.org/mosaik/mosaik-demo
  $ cd mosaik-demo
  $ pip install -r requirement.txt
  $ python demo.py

Concept
----------
4 main component

* mosaik Sim API(communicate between simulators and mosaik)
* Scenario API
* Simulator Manager(handle simulator processes)
* simulator(schedule)

4 module

* mosaik-core
* mosaik-componets(example simulator)
* mosaik-tools(analysis tools)
* Odysseus(big-data-analysis)

How to use
--------------
1. create simulation wrapper
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
1. define Meta Data::

    META = {
        'models': {
            'ExampleModel': {
                'public': True,
                'params': ['init_val'],
                'attrs': ['delta', 'val'],
            },
        },
    }

2. define Simulator Wrapper::

    class ExampleSim(mosaik_api.Simulator):
        def __init__(self):
            super().__init__(META)
            self.simulator = simulator.Simulator()
            self.eid_prefix = 'Model_'
            self.entities = {}  # Maps EIDs to model

        # additional simulator initializaiton
        def init(self, sid):
            return self.meta

        # model instance initializaiton
        def create(self, num, model, init_val):
            entities = []
            #
            # model creation
            #
            entities.append({'eid': eid, 'type': model})
            return entities

        def step(self, time, inputs):
            #
            # peform simulation step
            #
            return nexttime

        def get_data(self, query):
            #
            # construct returndata
            #
            return data

.. note::

  simulator wrapper is subclass of ``mosaiki_api.Simulator``

3. making it executable::

    def main():
        return mosaik_api.start_simulation(ExampleSim())

    if __name__ == '__main__':
        main()
