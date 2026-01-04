import React, { useState, useEffect, useMemo } from 'react';
import { 
  Check, 
  Plus, 
  X, 
  TrendingUp, 
  BookHeart,
  CheckSquare,
  MapPin,
  CalendarDays,
  ChevronLeft,
  ChevronRight,
  Sun,
  Settings,
  User,
  Activity,
  Zap,
  ZapOff,
  LayoutDashboard,
  Menu,
  Bell,
  Droplets,
  CreditCard,
  Mail,
  Shield,
  LogOut,
  Cloud,
  CloudRain,
  CloudLightning,
  CloudSnow,
  Wind
} from 'lucide-react';

// --- Components ---

const GlassCard = ({ children, className = '', hoverEffect = false, onClick = undefined }) => (
  <div 
    onClick={onClick}
    className={`relative overflow-hidden rounded-[24px] border border-white/20 bg-white/10 backdrop-blur-md shadow-[0_8px_32px_0_rgba(31,38,135,0.37)] ${hoverEffect ? 'transition-all duration-300 hover:bg-white/20 hover:border-white/30 hover:scale-[1.01]' : ''} ${className}`}
  >
    <div className="pointer-events-none absolute -inset-[100%] z-0 bg-[radial-gradient(circle_at_50%_0%,rgba(255,255,255,0.1)_0%,transparent_50%,transparent_100%)] blur-xl" />
    <div className="relative z-10 h-full w-full">
      {children}
    </div>
  </div>
);

// --- Sub-Components ---

const AppleClock = () => {
  const [time, setTime] = useState(new Date());
  useEffect(() => {
    const timer = setInterval(() => setTime(new Date()), 1000);
    return () => clearInterval(timer);
  }, []);
  const hours = time.toLocaleTimeString([], { hour: '2-digit', hour12: false }).split(':')[0];
  const minutes = time.toLocaleTimeString([], { minute: '2-digit' });
  return (
    <GlassCard hoverEffect className="h-full min-h-[280px] group">
      <div className="flex h-full flex-col items-center justify-center p-8 text-center text-white">
        <div className="flex flex-col items-center text-[6rem] lg:text-[7rem] font-bold leading-[0.85] tracking-tighter drop-shadow-2xl">
          <span>{hours}</span>
          <span>{minutes}</span>
        </div>
        <div className="mt-4 text-sm font-medium uppercase tracking-widest text-white/60">
           {time.toLocaleDateString([], { weekday: 'long', day: 'numeric' })}
        </div>
      </div>
    </GlassCard>
  );
};

// Weather Widget for Bhubaneswar
const WeatherWidget = () => {
  const [weather, setWeather] = useState({ 
    temp: '--', 
    condition: 'Loading...', 
    city: 'Bhubaneswar', 
    min: '--', 
    max: '--', 
    code: 0 
  });

  useEffect(() => {
    const fetchWeather = async () => {
      try {
        // Bhubaneswar Coordinates
        const res = await fetch(
          'https://api.open-meteo.com/v1/forecast?latitude=20.2961&longitude=85.8245&current=temperature_2m,weather_code,is_day&daily=temperature_2m_max,temperature_2m_min&timezone=auto'
        );
        const data = await res.json();
        
        if (!data.current || !data.daily) return;

        const code = data.current.weather_code;
        let condition = 'Clear';
        if (code >= 1 && code <= 3) condition = 'Cloudy';
        else if (code >= 45 && code <= 48) condition = 'Foggy';
        else if (code >= 51 && code <= 67) condition = 'Rain';
        else if (code >= 71 && code <= 86) condition = 'Snow';
        else if (code >= 95) condition = 'Thunderstorm';

        setWeather({
          temp: Math.round(data.current.temperature_2m),
          condition: condition,
          city: 'Bhubaneswar',
          min: Math.round(data.daily.temperature_2m_min[0]),
          max: Math.round(data.daily.temperature_2m_max[0]),
          code: code
        });
      } catch (error) {
        console.error("Weather error:", error);
        setWeather(prev => ({ ...prev, condition: 'Offline' }));
      }
    };

    fetchWeather();
    const interval = setInterval(fetchWeather, 1800000); // 30 mins
    return () => clearInterval(interval);
  }, []);

  const getWeatherIcon = (code) => {
    if (code === 0) return <Sun className="h-20 w-20 text-yellow-400 drop-shadow-[0_0_15px_rgba(250,204,21,0.6)]" />;
    if (code >= 1 && code <= 3) return <Cloud className="h-20 w-20 text-gray-300 drop-shadow-lg" />;
    if (code >= 45 && code <= 48) return <Wind className="h-20 w-20 text-gray-400" />;
    if (code >= 51 && code <= 67) return <CloudRain className="h-20 w-20 text-blue-400 drop-shadow-lg" />;
    if (code >= 71 && code <= 86) return <CloudSnow className="h-20 w-20 text-white drop-shadow-lg" />;
    if (code >= 95) return <CloudLightning className="h-20 w-20 text-yellow-300 drop-shadow-lg" />;
    return <Sun className="h-20 w-20 text-yellow-400" />;
  };

  return (
    <GlassCard hoverEffect className="h-full min-h-[180px] p-6 text-white flex flex-col justify-between relative overflow-hidden group">
      <div className="absolute -right-6 -top-6 z-0 opacity-50 transition-transform duration-700 group-hover:scale-110 group-hover:rotate-12">
         {getWeatherIcon(weather.code)}
      </div>
      <div className="relative z-10">
          <div className="flex flex-col">
              <h2 className="text-xl font-bold tracking-wide drop-shadow-md">{weather.city}</h2>
              <span className="text-6xl font-light tracking-tighter drop-shadow-xl mt-1">{weather.temp}°</span>
          </div>
      </div>
      <div className="relative z-10 flex flex-col gap-1">
          <div className="font-medium text-lg drop-shadow-md">{weather.condition}</div>
          <div className="text-sm font-medium text-white/70 flex gap-2">
             <span>H:{weather.max}°</span>
             <span>L:{weather.min}°</span>
          </div>
      </div>
    </GlassCard>
  );
};

const LineGraph = ({ data }) => {
  if (!data || data.length === 0) return null;
  const width = 100; const height = 60; const padding = 5;
  const graphWidth = width - padding * 2; const graphHeight = height - padding * 2;
  const points = data.map((d, i) => {
    const x = padding + (i / (data.length - 1)) * graphWidth;
    const y = height - padding - (d.percent / 100) * graphHeight;
    return `${x},${y}`;
  }).join(' ');

  return (
    <div className="relative h-32 w-full mt-4">
      <svg className="h-full w-full overflow-visible" viewBox={`0 0 ${width} ${height}`} preserveAspectRatio="none">
        <defs>
          <linearGradient id="lineGradient" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stopColor="#60a5fa" stopOpacity="0.6" />
            <stop offset="100%" stopColor="#60a5fa" stopOpacity="0" />
          </linearGradient>
        </defs>
        <path d={`M${points.split(' ')[0]} ${points} L${width-padding},${height-padding} L${padding},${height-padding} Z`} fill="url(#lineGradient)" className="blur-sm" />
        <polyline points={points} fill="none" stroke="#60a5fa" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" vectorEffect="non-scaling-stroke" className="drop-shadow-lg" />
      </svg>
    </div>
  );
};

// --- Views ---

const DashboardHome = ({ habits, todos, moments, stats, actions, state }) => {
  return (
    <div className="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-4 animate-in fade-in slide-in-from-bottom-4 duration-500">
      <div className="col-span-1 row-span-2 md:col-span-2"><AppleClock /></div>
      <div className="col-span-1"><WeatherWidget /></div>

      <GlassCard hoverEffect className="col-span-1 flex flex-col justify-between p-6">
          <div className="flex justify-between items-start">
             <div>
                <h3 className="text-xs font-bold uppercase tracking-wider text-white/60">Consistency</h3>
                <div className="text-3xl font-bold text-white mt-1">{stats.todayPercent}%</div>
             </div>
             <div className="p-2 bg-blue-500/20 rounded-full"><TrendingUp className="h-5 w-5 text-blue-300" /></div>
          </div>
          <LineGraph data={stats.graphData} />
      </GlassCard>

      <GlassCard className="col-span-1 flex min-h-[340px] flex-col p-6 md:col-span-2 lg:col-span-3">
         <div className="mb-6 flex items-center justify-between">
            <div className="flex items-center gap-3">
               <div className="p-2 bg-purple-500/20 rounded-lg"><CalendarDays className="h-5 w-5 text-purple-300" /></div>
               <h3 className="text-lg font-bold text-white">Habits</h3>
            </div>
            <div className="flex gap-1 bg-white/5 rounded-lg p-1">
               <button onClick={() => {const d = new Date(state.selectedDate); d.setDate(d.getDate()-1); actions.setSelectedDate(d)}} className="p-1 hover:bg-white/10 rounded text-white/70"><ChevronLeft className="h-5 w-5" /></button>
               <button onClick={() => {const d = new Date(state.selectedDate); d.setDate(d.getDate()+1); actions.setSelectedDate(d)}} disabled={state.isToday} className={`p-1 rounded transition-colors ${state.isToday ? 'opacity-30' : 'hover:bg-white/10 text-white/70'}`}><ChevronRight className="h-5 w-5" /></button>
            </div>
         </div>
         <div className="custom-scrollbar flex-1 space-y-3 overflow-y-auto pr-2">
            <div className="grid grid-cols-1 gap-3 sm:grid-cols-2 lg:grid-cols-3">
            {habits.map(habit => {
               const isCompleted = habit.completedDates.includes(state.selectedDateString);
               return (
                  <div key={habit.id} onClick={() => actions.toggleHabit(habit.id)} className={`group relative cursor-pointer overflow-hidden rounded-xl border p-4 transition-all duration-300 ${isCompleted ? 'border-blue-400/50 bg-blue-500/20' : 'border-white/10 bg-white/5 hover:bg-white/10'}`}>
                     <div className={`absolute bottom-0 left-0 z-0 h-full bg-blue-500/20 transition-all duration-500 ${isCompleted ? 'w-full' : 'w-0'}`} />
                     <div className="relative z-10 flex items-center justify-between">
                        <span className={`font-medium ${isCompleted ? 'text-white' : 'text-white/70'}`}>{habit.name}</span>
                        <div className={`flex h-6 w-6 items-center justify-center rounded-full border ${isCompleted ? 'border-blue-400 bg-blue-500 text-white' : 'border-white/30'}`}>{isCompleted && <Check className="h-3 w-3 stroke-[3]" />}</div>
                     </div>
                     <button onClick={(e) => { e.stopPropagation(); actions.deleteHabit(habit.id); }} className="absolute right-2 top-2 z-20 text-white/30 opacity-0 group-hover:opacity-100 hover:text-red-300"><X className="h-3 w-3" /></button>
                  </div>
               )
            })}
            <form onSubmit={actions.addHabit} className="flex h-full min-h-[60px] items-center justify-center rounded-xl border border-dashed border-white/20 bg-white/5 hover:bg-white/10">
               <input value={state.newHabit} onChange={e => actions.setNewHabit(e.target.value)} placeholder="+ Add Habit" className="w-full bg-transparent text-center text-sm text-white/70 placeholder-white/30 focus:outline-none" />
            </form>
            </div>
         </div>
      </GlassCard>

      <GlassCard className="col-span-1 row-span-2 flex h-full min-h-[320px] flex-col p-6">
         <div className="mb-4 flex items-center justify-between">
            <div className="flex items-center gap-3">
                <div className="p-2 bg-blue-500/20 rounded-lg"><CheckSquare className="h-5 w-5 text-blue-300" /></div>
                <h3 className="font-bold text-white">Tasks</h3>
            </div>
            <span className="rounded-full bg-white/10 px-2 py-0.5 text-xs font-bold text-white/70">{todos.filter(t => !t.completed).length}</span>
         </div>
         <div className="custom-scrollbar flex-1 space-y-2 overflow-y-auto pr-1">
           {todos.map(todo => (
             <div key={todo.id} className="group flex items-start gap-3 rounded-xl border border-white/10 bg-white/5 p-3 hover:bg-white/10">
               <button onClick={() => actions.toggleTodo(todo.id)} className={`mt-0.5 flex h-5 w-5 flex-shrink-0 items-center justify-center rounded border transition-all ${todo.completed ? 'border-blue-400 bg-blue-500' : 'border-white/30 hover:border-blue-400'}`}>
                 {todo.completed && <Check className="h-3 w-3 text-white" />}
               </button>
               <span className={`flex-1 text-sm ${todo.completed ? 'text-white/40 line-through' : 'text-white/80'}`}>{todo.text}</span>
               <button onClick={() => actions.deleteTodo(todo.id)} className="text-white/30 opacity-0 hover:text-red-300 group-hover:opacity-100"><X className="h-3 w-3" /></button>
             </div>
           ))}
         </div>
         <form onSubmit={actions.addTodo} className="mt-3"><input value={state.newTodo} onChange={e => actions.setNewTodo(e.target.value)} placeholder="+ New Task" className="w-full rounded-xl border border-white/10 bg-white/5 px-3 py-2 text-sm text-white focus:bg-white/10 focus:outline-none" /></form>
      </GlassCard>

      <GlassCard className="col-span-1 flex h-full min-h-[240px] flex-col p-6">
          <div className="mb-4 flex items-center gap-3">
             <div className="p-2 bg-pink-500/20 rounded-lg"><BookHeart className="h-5 w-5 text-pink-300" /></div>
             <h3 className="font-bold text-white">Journal</h3>
          </div>
          <textarea value={moments[state.selectedDateString] || ''} onChange={(e) => actions.updateMoments({...moments, [state.selectedDateString]: e.target.value})} placeholder="Write about today..." className="custom-scrollbar flex-1 w-full resize-none rounded-xl bg-white/5 p-3 text-sm text-white/90 placeholder-white/30 focus:bg-white/10 focus:outline-none" />
      </GlassCard>
    </div>
  );
};

const SettingsView = ({ displayName, setDisplayName, reduceMotion, setReduceMotion }) => {
  const [localName, setLocalName] = useState(displayName);
  const [activeTab, setActiveTab] = useState('profile');
  const [mockId] = useState(() => Math.random().toString(36).substr(2, 9));

  const saveProfile = () => {
     if(localName !== displayName) {
         setDisplayName(localName);
         localStorage.setItem('habit_profile_name', localName);
     }
  };

  return (
    <div className="max-w-5xl mx-auto animate-in fade-in slide-in-from-bottom-8 duration-500">
       <h1 className="text-3xl font-bold text-white mb-8">Settings</h1>
       
       <div className="grid grid-cols-1 lg:grid-cols-12 gap-8">
          <div className="lg:col-span-4 space-y-2">
             <GlassCard className="p-2">
                {[
                    { id: 'profile', icon: User, label: 'My Profile' },
                    { id: 'display', icon: Activity, label: 'Appearance' },
                    { id: 'notifications', icon: Bell, label: 'Notifications' },
                ].map(item => (
                    <button key={item.id} onClick={() => setActiveTab(item.id)} className={`w-full flex items-center gap-3 px-4 py-3 rounded-xl text-sm font-medium transition-all ${activeTab === item.id ? 'bg-blue-500/20 text-blue-200' : 'text-white/60 hover:bg-white/5 hover:text-white'}`}>
                        <item.icon className="w-4 h-4" />{item.label}
                    </button>
                ))}
             </GlassCard>
             <GlassCard className="p-4 mt-4">
                <div className="p-4 bg-gradient-to-br from-indigo-500/20 to-purple-500/20 rounded-xl border border-white/10 text-center">
                    <div className="w-10 h-10 mx-auto bg-white/10 rounded-full flex items-center justify-center mb-2"><Zap className="w-5 h-5 text-yellow-300" /></div>
                    <h3 className="font-bold text-white">Upgrade to Pro</h3>
                    <p className="text-xs text-white/60 mt-1 mb-3">Unlock unlimited history and AI insights.</p>
                    <button className="w-full py-2 bg-white text-black font-bold text-xs rounded-lg hover:bg-white/90">Upgrade Plan</button>
                </div>
             </GlassCard>
          </div>

          <div className="lg:col-span-8">
             <GlassCard className="p-8 min-h-[500px]">
                {activeTab === 'profile' && (
                    <div className="space-y-6">
                        <div className="flex items-center gap-6 pb-6 border-b border-white/10">
                            <div className="w-24 h-24 rounded-full bg-gradient-to-tr from-blue-400 to-purple-500 flex items-center justify-center text-3xl font-bold text-white shadow-xl">{displayName?.[0] || 'U'}</div>
                            <div>
                                <h2 className="text-xl font-bold text-white">Public Profile</h2>
                                <p className="text-sm text-white/50">This is how you appear in the app.</p>
                            </div>
                        </div>
                        <div className="space-y-4">
                            <div>
                                <label className="block text-xs font-bold text-white/40 uppercase tracking-wider mb-2">Display Name</label>
                                <input value={localName} onChange={(e) => setLocalName(e.target.value)} className="w-full bg-white/5 border border-white/10 rounded-xl px-4 py-3 text-white focus:outline-none focus:border-blue-500/50" />
                            </div>
                             <div>
                                <label className="block text-xs font-bold text-white/40 uppercase tracking-wider mb-2">Local ID</label>
                                <div className="flex items-center gap-2 w-full bg-white/5 border border-white/10 rounded-xl px-4 py-3 text-white/50"><Shield className="w-4 h-4" /><span>anon_{mockId}</span></div>
                            </div>
                            <div className="pt-4 flex justify-end">
                                <button onClick={saveProfile} className="px-6 py-2 bg-blue-600 hover:bg-blue-500 text-white rounded-lg font-medium transition-colors">Save Changes</button>
                            </div>
                        </div>
                    </div>
                )}
                {activeTab === 'display' && (
                    <div className="space-y-6">
                         <h2 className="text-xl font-bold text-white pb-4 border-b border-white/10">Appearance</h2>
                         <div className="flex items-center justify-between p-4 bg-white/5 rounded-xl border border-white/10">
                            <div className="flex items-center gap-3">
                                {reduceMotion ? <ZapOff className="w-5 h-5 text-white/60" /> : <Zap className="w-5 h-5 text-yellow-300" />}
                                <div>
                                    <div className="font-medium text-white">Reduced Motion</div>
                                    <div className="text-xs text-white/50">Disable background mesh animations</div>
                                </div>
                            </div>
                            <button onClick={() => setReduceMotion(!reduceMotion)} className={`w-12 h-7 rounded-full transition-colors relative ${reduceMotion ? 'bg-blue-600' : 'bg-white/20'}`}>
                                <div className={`absolute top-1 w-5 h-5 bg-white rounded-full transition-all ${reduceMotion ? 'left-6' : 'left-1'}`} />
                            </button>
                         </div>
                    </div>
                )}
                {activeTab === 'notifications' && (
                    <div className="space-y-6">
                         <h2 className="text-xl font-bold text-white pb-4 border-b border-white/10">Notifications</h2>
                         <p className="text-white/60 text-sm">Notification settings are managed by your device.</p>
                    </div>
                )}
             </GlassCard>
          </div>
       </div>
    </div>
  );
}

// --- Main App ---

const App = () => {
  const [displayName, setDisplayName] = useState(() => {
      try { return localStorage.getItem('habit_profile_name') || 'Friend'; } catch { return 'Friend'; }
  });
  const [view, setView] = useState('home'); 
  const [reduceMotion, setReduceMotion] = useState(() => {
      try { return JSON.parse(localStorage.getItem('habit_reduce_motion')) || false; } catch { return false; }
  });
  const [mobileMenuOpen, setMobileMenuOpen] = useState(false);

  // Data State with error handling
  const [habits, setHabits] = useState(() => {
      try { return JSON.parse(localStorage.getItem('habit_data_habits')) || []; } catch { return []; }
  });
  const [todos, setTodos] = useState(() => {
      try { return JSON.parse(localStorage.getItem('habit_data_todos')) || []; } catch { return []; }
  });
  const [moments, setMoments] = useState(() => {
      try { return JSON.parse(localStorage.getItem('habit_data_moments')) || {}; } catch { return {}; }
  });
  
  const [newHabit, setNewHabit] = useState('');
  const [newTodo, setNewTodo] = useState('');
  const [selectedDate, setSelectedDate] = useState(new Date());

  // Persistence Effects
  useEffect(() => { localStorage.setItem('habit_data_habits', JSON.stringify(habits)); }, [habits]);
  useEffect(() => { localStorage.setItem('habit_data_todos', JSON.stringify(todos)); }, [todos]);
  useEffect(() => { localStorage.setItem('habit_data_moments', JSON.stringify(moments)); }, [moments]);
  useEffect(() => { localStorage.setItem('habit_reduce_motion', JSON.stringify(reduceMotion)); }, [reduceMotion]);

  const getDayString = (date) => {
    const offset = date.getTimezoneOffset() * 60000;
    return new Date(date.getTime() - offset).toISOString().split('T')[0];
  };
  const todayString = getDayString(new Date());
  const selectedDateString = getDayString(selectedDate);
  const isToday = selectedDateString === todayString;

  const actions = {
      toggleHabit: (id) => setHabits(habits.map(h => h.id === id ? { ...h, completedDates: h.completedDates.includes(selectedDateString) ? h.completedDates.filter(d => d !== selectedDateString) : [...h.completedDates, selectedDateString] } : h)),
      deleteHabit: (id) => setHabits(habits.filter(h => h.id !== id)),
      addHabit: (e) => { e.preventDefault(); if(newHabit.trim()) { setHabits([...habits, { id: Date.now(), name: newHabit, completedDates: [] }]); setNewHabit(''); } },
      setNewHabit,
      toggleTodo: (id) => setTodos(todos.map(t => t.id === id ? { ...t, completed: !t.completed } : t)),
      deleteTodo: (id) => setTodos(todos.filter(t => t.id !== id)),
      addTodo: (e) => { e.preventDefault(); if(newTodo.trim()) { setTodos([...todos, { id: Date.now(), text: newTodo, completed: false }]); setNewTodo(''); } },
      setNewTodo,
      updateMoments: (newMoments) => setMoments(newMoments),
      setSelectedDate
  };

  const stats = useMemo(() => {
    const completed = habits.filter(h => h.completedDates.includes(selectedDateString)).length;
    const todayPercent = habits.length ? Math.round((completed / habits.length) * 100) : 0;
    const graphData = Array.from({ length: 7 }, (_, i) => {
        const d = new Date(); d.setDate(d.getDate() - 6 + i);
        const ds = getDayString(d);
        const c = habits.filter(h => h.completedDates.includes(ds)).length;
        return { percent: habits.length ? Math.round((c / habits.length) * 100) : 0 };
    });
    return { todayPercent, graphData };
  }, [habits, selectedDateString]);

  return (
    <div className="min-h-screen bg-[conic-gradient(at_top_left,_var(--tw-gradient-stops))] from-indigo-950 via-purple-950 to-slate-950 text-white selection:bg-blue-500/50 flex">
        {!reduceMotion && (
            <div className="fixed inset-0 z-0">
                <div className="absolute left-1/4 top-1/4 h-96 w-96 animate-pulse rounded-full bg-blue-600/20 blur-[128px]" />
                <div className="absolute bottom-1/4 right-1/4 h-96 w-96 animate-pulse rounded-full bg-purple-600/20 blur-[128px]" style={{animationDelay: '2s'}} />
            </div>
        )}

        {/* Sidebar */}
        <aside className={`fixed inset-y-0 left-0 z-50 w-64 transform transition-transform duration-300 ease-in-out lg:relative lg:translate-x-0 ${mobileMenuOpen ? 'translate-x-0' : '-translate-x-full'} lg:block`}>
           <div className="h-full p-4 flex flex-col">
              <GlassCard className="h-full flex flex-col p-4 bg-white/5 backdrop-blur-xl border-white/10">
                  <div className="flex items-center gap-3 px-2 py-4 mb-6">
                      <div className="w-8 h-8 rounded-lg bg-gradient-to-tr from-blue-400 to-purple-500 shadow-lg flex items-center justify-center">
                          <Droplets className="w-5 h-5 text-white" />
                      </div>
                      <span className="font-bold text-lg tracking-tight">Habit</span>
                  </div>
                  
                  <nav className="space-y-1 flex-1">
                      {[
                          { id: 'home', icon: LayoutDashboard, label: 'Overview' },
                          { id: 'journal', icon: BookHeart, label: 'Journal' },
                          { id: 'settings', icon: Settings, label: 'Settings' },
                      ].map(item => (
                          <button 
                            key={item.id}
                            onClick={() => { setView(item.id); setMobileMenuOpen(false); }}
                            className={`w-full flex items-center gap-3 px-3 py-3 rounded-xl text-sm font-medium transition-all ${view === item.id ? 'bg-white/10 text-white shadow-inner border border-white/5' : 'text-white/50 hover:bg-white/5 hover:text-white'}`}
                          >
                             <item.icon className="w-5 h-5" />
                             {item.label}
                          </button>
                      ))}
                  </nav>

                  <div className="pt-4 mt-4 border-t border-white/10">
                      <div className="flex items-center gap-3 px-2 py-2">
                          <div className="w-8 h-8 rounded-full bg-gradient-to-tr from-pink-400 to-orange-400 flex items-center justify-center font-bold text-xs shadow-md">
                              {displayName?.[0] || 'U'}
                          </div>
                          <div className="flex-1 overflow-hidden">
                              <div className="text-sm font-bold truncate">{displayName}</div>
                              <div className="text-xs text-white/40 truncate">Free Plan</div>
                          </div>
                      </div>
                  </div>
              </GlassCard>
           </div>
        </aside>

        {/* Mobile Overlay */}
        {mobileMenuOpen && <div className="fixed inset-0 z-40 bg-black/50 lg:hidden backdrop-blur-sm" onClick={() => setMobileMenuOpen(false)} />}

        {/* Main Content */}
        <main className="flex-1 relative z-10 h-screen overflow-y-auto custom-scrollbar">
            <div className="p-4 lg:p-8 max-w-[1600px] mx-auto">
                <div className="lg:hidden flex items-center justify-between mb-6">
                    <button onClick={() => setMobileMenuOpen(true)} className="p-2 bg-white/10 rounded-lg"><Menu className="w-6 h-6" /></button>
                    <span className="font-bold">Habit</span>
                    <div className="w-10" />
                </div>

                {view === 'home' && <DashboardHome habits={habits} todos={todos} moments={moments} stats={stats} actions={actions} state={{selectedDate, selectedDateString, isToday, newHabit, newTodo}} />}
                
                {view === 'journal' && (
                    <div className="max-w-2xl mx-auto animate-in fade-in slide-in-from-bottom-4 duration-500">
                        <h1 className="text-3xl font-bold mb-6">Journal</h1>
                        <div className="space-y-4">
                            {Object.entries(moments).length === 0 ? <div className="text-center text-white/40 py-10">No entries yet.</div> : 
                                Object.entries(moments).sort().reverse().map(([date, text]) => (
                                <GlassCard key={date} className="p-6">
                                    <div className="text-sm text-white/40 font-mono mb-2">{date}</div>
                                    <p className="whitespace-pre-wrap leading-relaxed">{text}</p>
                                </GlassCard>
                            ))}
                        </div>
                    </div>
                )}

                {view === 'settings' && <SettingsView displayName={displayName} setDisplayName={setDisplayName} reduceMotion={reduceMotion} setReduceMotion={setReduceMotion} />}
            </div>
        </main>
        
        <style jsx global>{`
            .custom-scrollbar::-webkit-scrollbar { width: 6px; }
            .custom-scrollbar::-webkit-scrollbar-track { background: transparent; }
            .custom-scrollbar::-webkit-scrollbar-thumb { background: rgba(255,255,255,0.1); border-radius: 10px; }
            .custom-scrollbar::-webkit-scrollbar-thumb:hover { background: rgba(255,255,255,0.2); }
        `}</style>
    </div>
  );
};

export default App;


