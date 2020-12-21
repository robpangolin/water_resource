from pywr.core import Model, Input, Output

import pandas as pd
model = Model()

supply = Input(model, name = 'supply')
demand = Output(model, name='demand')
supply.connect(demand)

supply.max_flow = 10.0
demand.max_flow = 10.0

supply.cost = 3.0
demand.cost = -100.0

import datetime
from pywr.core import Timestepper

model.timestepper = Timestepper(
pd.to_datetime('2015-01-01'),
pd.to_datetime('2015-12-31'),
datetime.timedelta(1)
)

from pywr.recorders import NumpyArrayNodeRecorder

recorder = NumpyArrayNodeRecorder(model, supply)

model.run()
