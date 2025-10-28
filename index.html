import React, { useState, useEffect } from 'react';
import { Search, Plus, Edit2, Trash2, X, Save, Check, AlertCircle, BookOpen, Users, Filter, Mail, History, Shield } from 'lucide-react';

export default function PharmaDrugApp() {
  const [drugs, setDrugs] = useState([]);
  const [pendingDrugs, setPendingDrugs] = useState([]);
  const [drugClasses, setDrugClasses] = useState([]);
  const [users, setUsers] = useState([]);
  const [editHistory, setEditHistory] = useState([]);
  const [searchTerm, setSearchTerm] = useState('');
  const [keywordFilter, setKeywordFilter] = useState('');
  const [showAddForm, setShowAddForm] = useState(false);
  const [showClassForm, setShowClassForm] = useState(false);
  const [editingDrug, setEditingDrug] = useState(null);
  const [editingClass, setEditingClass] = useState(null);
  const [loading, setLoading] = useState(true);
  const [currentUser, setCurrentUser] = useState(null);
  const [activeTab, setActiveTab] = useState('drugs');
  const [confirmerName, setConfirmerName] = useState('');
  const [loginMode, setLoginMode] = useState(null);
  const [showUsersList, setShowUsersList] = useState(false);
  const [showKeywordFilter, setShowKeywordFilter] = useState(false);
  const [showAdminPanel, setShowAdminPanel] = useState(false);
  
  const [loginData, setLoginData] = useState({
    email: '',
    code: ''
  });

  const [registrationData, setRegistrationData] = useState({
    nickname: '',
    email: '',
    medSchoolYear: '',
    code: ''
  });

  const [formData, setFormData] = useState({
    name: '',
    drugClass: '',
    indications: '',
    contraindications: '',
    adverseEffects: '',
    boxWarning: '',
    routes: [],
    dosages: [{indication: '', amount: '', unit: ''}],
    notes: '',
    submittedBy: ''
  });

  const [classFormData, setClassFormData] = useState({
    name: '',
    conditionClass: '',
    description: '',
    mechanism: '',
    commonSideEffects: '',
    notes: '',
    selectedDrugs: [],
    submittedBy: ''
  });

  const routeOptions = ['Oral', 'Intravenous', 'Intramuscular', 'Subcutaneous', 'Topical', 'Patch', 'Inhalation', 'Rectal', 'Sublingual', 'Ophthalmic', 'Otic', 'Nasal'];

  useEffect(() => {
    loadData();
  }, []);

  const loadData = async () => {
    try {
      const drugsResult = await window.storage.get('pharma-drugs-approved', true);
      const pendingResult = await window.storage.get('pharma-drugs-pending', true);
      const classesResult = await window.storage.get('pharma-drug-classes', true);
      const usersResult = await window.storage.get('pharma-users', true);
      const historyResult = await window.storage.get('pharma-edit-history', true);
      const userResult = await window.storage.get('pharma-current-user');
      
      if (drugsResult && drugsResult.value) setDrugs(JSON.parse(drugsResult.value));
      if (pendingResult && pendingResult.value) setPendingDrugs(JSON.parse(pendingResult.value));
      if (classesResult && classesResult.value) setDrugClasses(JSON.parse(classesResult.value));
      if (usersResult && usersResult.value) setUsers(JSON.parse(usersResult.value));
      if (historyResult && historyResult.value) setEditHistory(JSON.parse(historyResult.value));
      if (userResult && userResult.value) setCurrentUser(JSON.parse(userResult.value));
    } catch (error) {
      console.log('No existing data found, starting fresh');
    } finally {
      setLoading(false);
    }
  };

  const isAdmin = () => {
    return currentUser && currentUser.nickname === 'MagoMago' && currentUser.email.toLowerCase() === 'suvibuii@gmail.com';
  };

  const addToHistory = async (action, itemType, itemName, details) => {
    const historyEntry = {
      id: Date.now().toString(),
      action,
      itemType,
      itemName,
      details,
      userNickname: currentUser.nickname,
      userEmail: currentUser.email,
      timestamp: new Date().toISOString()
    };

    const updatedHistory = [historyEntry, ...editHistory];
    try {
      await window.storage.set('pharma-edit-history', JSON.stringify(updatedHistory), true);
      setEditHistory(updatedHistory);
    } catch (error) {
      console.error('Error saving history:', error);
    }
  };

  const handleRegister = async () => {
    if (!registrationData.nickname.trim() || !registrationData.email.trim() || !registrationData.medSchoolYear.trim() || !registrationData.code.trim()) {
      alert('All fields are required');
      return;
    }

    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!emailRegex.test(registrationData.email)) {
      alert('Please enter a valid email address');
      return;
    }

    if (registrationData.code.length !== 6 || !/^\d+$/.test(registrationData.code)) {
      alert('Code must be exactly 6 digits');
      return;
    }

    if (users.some(u => u.email.toLowerCase() === registrationData.email.toLowerCase())) {
      alert('This email is already registered');
      return;
    }

    if (users.some(u => u.nickname.toLowerCase() === registrationData.nickname.toLowerCase())) {
      alert('This nickname is already taken');
      return;
    }

    if (registrationData.nickname.toLowerCase() === 'magomago' && registrationData.email.toLowerCase() !== 'suvibuii@gmail.com') {
      alert('The nickname "MagoMago" is reserved');
      return;
    }

    const user = {
      nickname: registrationData.nickname.trim(),
      email: registrationData.email.trim().toLowerCase(),
      medSchoolYear: registrationData.medSchoolYear.trim(),
      code: registrationData.code,
      registeredDate: new Date().toISOString()
    };

    const updatedUsers = [...users, user];
    
    try {
      await window.storage.set('pharma-users', JSON.stringify(updatedUsers), true);
      await window.storage.set('pharma-current-user', JSON.stringify(user));
      setUsers(updatedUsers);
      setCurrentUser(user);
    } catch (error) {
      console.error('Error saving user:', error);
      alert('Failed to register. Please try again.');
    }
  };

  const handleLogin = async () => {
    if (!loginData.email.trim() || !loginData.code.trim()) {
      alert('Email and code are required');
      return;
    }

    const user = users.find(u => u.email.toLowerCase() === loginData.email.toLowerCase() && u.code === loginData.code);
    
    if (!user) {
      alert('Invalid email or code');
      return;
    }

    try {
      await window.storage.set('pharma-current-user', JSON.stringify(user));
      setCurrentUser(user);
    } catch (error) {
      console.error('Error logging in:', error);
      alert('Failed to log in. Please try again.');
    }
  };

  const handleForgotCode = () => {
    const email = prompt('Enter your registered email address:');
    if (!email) return;
    
    const user = users.find(u => u.email.toLowerCase() === email.toLowerCase());
    if (user) {
      alert(`Password reset link would be sent to ${email}. (This is a demo - in production, an email would be sent with a reset link)`);
    } else {
      alert('Email not found in our system');
    }
  };

  const handleLogout = async () => {
    try {
      await window.storage.set('pharma-current-user', '');
      setCurrentUser(null);
      setLoginMode(null);
    } catch (error) {
      console.error('Error logging out:', error);
    }
  };

  const saveDrugs = async (updatedDrugs) => {
    try {
      await window.storage.set('pharma-drugs-approved', JSON.stringify(updatedDrugs), true);
      setDrugs(updatedDrugs);
    } catch (error) {
      console.error('Error saving drugs:', error);
      alert('Failed to save data. Please try again.');
    }
  };

  const savePendingDrugs = async (updatedPending) => {
    try {
      await window.storage.set('pharma-drugs-pending', JSON.stringify(updatedPending), true);
      setPendingDrugs(updatedPending);
    } catch (error) {
      console.error('Error saving pending drugs:', error);
      alert('Failed to save data. Please try again.');
    }
  };

  const saveDrugClasses = async (updatedClasses) => {
    try {
      await window.storage.set('pharma-drug-classes', JSON.stringify(updatedClasses), true);
      setDrugClasses(updatedClasses);
    } catch (error) {
      console.error('Error saving drug classes:', error);
      alert('Failed to save data. Please try again.');
    }
  };

  const handleAddDrug = async () => {
    if (!formData.name.trim() || !formData.submittedBy.trim()) {
      alert('Drug name and your name are required');
      return;
    }

    const newDrug = {
      id: Date.now().toString(),
      ...formData,
      indications: formData.indications.split(',').map(i => i.trim()).filter(i => i),
      dateSubmitted: new Date().toISOString(),
      submitterNickname: currentUser.nickname,
      submitterEmail: currentUser.email,
      confirmations: [],
      status: 'pending'
    };

    await savePendingDrugs([...pendingDrugs, newDrug]);
    await addToHistory('submitted', 'drug', formData.name, 'Submitted new drug for approval');
    resetForm();
    setActiveTab('pending');
    alert('Drug submitted for approval!');
  };

  const handleUpdateDrug = async () => {
    if (!formData.submittedBy.trim()) {
      alert('Your name is required');
      return;
    }

    const updatedDrug = {
      ...editingDrug,
      ...formData,
      indications: formData.indications.split(',').map(i => i.trim()).filter(i => i),
      dateModified: new Date().toISOString(),
      modifiedBy: formData.submittedBy,
      modifierNickname: currentUser.nickname,
      modifierEmail: currentUser.email,
      confirmations: [],
      status: 'pending'
    };

    const updatedApproved = drugs.filter(drug => drug.id !== editingDrug.id);
    await saveDrugs(updatedApproved);
    await savePendingDrugs([...pendingDrugs, updatedDrug]);
    await addToHistory('edited', 'drug', formData.name, 'Edited drug (pending reapproval)');
    
    resetForm();
    setActiveTab('pending');
    alert('Changes submitted for approval!');
  };

  const handleAdminEdit = async (drug) => {
    if (!window.confirm('As admin, you can edit this drug directly without approval. Continue?')) return;
    
    const updatedDrugs = drugs.map(d => d.id === drug.id ? {...d, ...formData, indications: formData.indications.split(',').map(i => i.trim()).filter(i => i)} : d);
    await saveDrugs(updatedDrugs);
    await addToHistory('admin-edit', 'drug', formData.name, 'Direct admin edit');
    resetForm();
    alert('Drug updated directly (admin privileges)');
  };

  const handleConfirmDrug = async (drugId, name) => {
    if (!name.trim()) {
      alert('Please enter your name to confirm');
      return;
    }

    const drug = pendingDrugs.find(d => d.id === drugId);
    if (!drug) return;

    const confirmationEntry = {
      nickname: name,
      email: currentUser.email,
      date: new Date().toISOString()
    };

    if (drug.confirmations.some(c => c.email === currentUser.email)) {
      alert('You have already confirmed this drug');
      return;
    }

    const updatedConfirmations = [...drug.confirmations, confirmationEntry];
    
    const isSuviApproved = currentUser.email.toLowerCase() === 'suvibuii@gmail.com' || 
                           updatedConfirmations.some(c => c.email.toLowerCase() === 'suvibuii@gmail.com');
    const hasTwoConfirmations = updatedConfirmations.length >= 2;

    if (isSuviApproved || hasTwoConfirmations) {
      const approvedDrug = {
        ...drug,
        confirmations: updatedConfirmations,
        status: 'approved',
        dateApproved: new Date().toISOString()
      };
      
      await saveDrugs([...drugs, approvedDrug]);
      await savePendingDrugs(pendingDrugs.filter(d => d.id !== drugId));
      await addToHistory('approved', 'drug', drug.name, `Approved by ${name}`);
      setConfirmerName('');
      alert('Drug approved and added to directory!');
    } else {
      const updatedPending = pendingDrugs.map(d =>
        d.id === drugId ? { ...d, confirmations: updatedConfirmations } : d
      );
      await savePendingDrugs(updatedPending);
      setConfirmerName('');
      alert(`Confirmation recorded (${updatedConfirmations.length}/2)`);
    }
  };

  const handleDeleteDrug = async (id) => {
    const drug = drugs.find(d => d.id === id);
    if (window.confirm('Are you sure you want to delete this drug?')) {
      await saveDrugs(drugs.filter(drug => drug.id !== id));
      await addToHistory('deleted', 'drug', drug.name, 'Deleted from directory');
    }
  };

  const handleDeletePending = async (id) => {
    const drug = pendingDrugs.find(d => d.id === id);
    if (window.confirm('Are you sure you want to reject this submission?')) {
      await savePendingDrugs(pendingDrugs.filter(drug => drug.id !== id));
      await addToHistory('rejected', 'drug', drug.name, 'Rejected submission');
    }
  };

  const handleAddClass = async () => {
    if (!classFormData.name.trim() || !classFormData.submittedBy.trim()) {
      alert('Class name and your name are required');
      return;
    }

    const newClass = {
      id: Date.now().toString(),
      ...classFormData,
      dateAdded: new Date().toISOString(),
      submitterNickname: currentUser.nickname,
      submitterEmail: currentUser.email
    };

    await saveDrugClasses([...drugClasses, newClass]);
    await addToHistory('created', 'drug class', classFormData.name, 'Created new drug class');
    resetClassForm();
  };

  const handleUpdateClass = async () => {
    const updatedClasses = drugClasses.map(cls =>
      cls.id === editingClass.id ? { ...cls, ...classFormData, modifiedBy: currentUser.nickname } : cls
    );
    await saveDrugClasses(updatedClasses);
    await addToHistory('edited', 'drug class', classFormData.name, 'Updated drug class');
    resetClassForm();
  };

  const handleDeleteClass = async (id) => {
    const cls = drugClasses.find(c => c.id === id);
    if (window.confirm('Are you sure you want to delete this drug class?')) {
      await saveDrugClasses(drugClasses.filter(cls => cls.id !== id));
      await addToHistory('deleted', 'drug class', cls.name, 'Deleted drug class');
    }
  };

  const resetForm = () => {
    setFormData({
      name: '',
      drugClass: '',
      indications: '',
      contraindications: '',
      adverseEffects: '',
      boxWarning: '',
      routes: [],
      dosages: [{indication: '', amount: '', unit: ''}],
      notes: '',
      submittedBy: currentUser ? currentUser.nickname : ''
    });
    setShowAddForm(false);
    setEditingDrug(null);
  };

  const resetClassForm = () => {
    setClassFormData({
      name: '',
      conditionClass: '',
      description: '',
      mechanism: '',
      commonSideEffects: '',
      notes: '',
      selectedDrugs: [],
      submittedBy: currentUser ? currentUser.nickname : ''
    });
    setShowClassForm(false);
    setEditingClass(null);
  };

  const startEdit = (drug) => {
    setEditingDrug(drug);
    setFormData({
      name: drug.name,
      drugClass: drug.drugClass || '',
      indications: drug.indications.join(', '),
      contraindications: drug.contraindications || '',
      adverseEffects: drug.adverseEffects || '',
      boxWarning: drug.boxWarning || '',
      routes: drug.routes || [],
      dosages: drug.dosages || [{indication: '', amount: '', unit: ''}],
      notes: drug.notes,
      submittedBy: currentUser.nickname
    });
    setShowAddForm(true);
    setActiveTab('drugs');
  };

  const startEditClass = (cls) => {
    setEditingClass(cls);
    setClassFormData({
      name: cls.name,
      conditionClass: cls.conditionClass || '',
      description: cls.description,
      mechanism: cls.mechanism,
      commonSideEffects: cls.commonSideEffects,
      notes: cls.notes,
      selectedDrugs: cls.selectedDrugs || [],
      submittedBy: currentUser.nickname
    });
    setShowClassForm(true);
  };

  const getKeywordMatches = (item, keywords) => {
    const searchText = `${item.name} ${item.indications?.join(' ')} ${item.contraindications} ${item.adverseEffects} ${item.drugClass} ${item.notes}`.toLowerCase();
    return keywords.filter(kw => searchText.includes(kw.toLowerCase())).length;
  };

  const filterByKeywords = () => {
    if (!keywordFilter.trim()) return drugs;
    
    const keywords = keywordFilter.split(',').map(k => k.trim()).filter(k => k);
    const drugsWithScores = drugs.map(drug => ({
      ...drug,
      matchCount: getKeywordMatches(drug, keywords)
    }));
    
    return drugsWithScores
      .filter(d => d.matchCount > 0)
      .sort((a, b) => b.matchCount - a.matchCount);
  };

  const filteredDrugs = showKeywordFilter ? filterByKeywords() : drugs.filter(drug => {
    const search = searchTerm.toLowerCase();
    return (
      drug.name.toLowerCase().includes(search) ||
      (drug.drugClass && drug.drugClass.toLowerCase().includes(search)) ||
      drug.indications.some(ind => ind.toLowerCase().includes(search)) ||
      (drug.contraindications && drug.contraindications.toLowerCase().includes(search)) ||
      (drug.adverseEffects && drug.adverseEffects.toLowerCase().includes(search)) ||
      drug.notes.toLowerCase().includes(search)
    );
  });

  const filteredClasses = drugClasses.filter(cls => {
    const search = searchTerm.toLowerCase();
    return (
      cls.name.toLowerCase().includes(search) ||
      cls.description.toLowerCase().includes(search) ||
      cls.mechanism.toLowerCase().includes(search) ||
      (cls.conditionClass && cls.conditionClass.toLowerCase().includes(search))
    );
  });

  const getDrugsByClass = (className) => {
    return drugs.filter(drug => drug.drugClass === className);
  };

  const toggleRoute = (route) => {
    setFormData(prev => ({
      ...prev,
      routes: prev.routes.includes(route) 
        ? prev.routes.filter(r => r !== route)
        : [...prev.routes, route]
    }));
  };

  const addDosage = () => {
    setFormData(prev => ({
      ...prev,
      dosages: [...prev.dosages, {indication: '', amount: '', unit: ''}]
    }));
  };

  const updateDosage = (index, field, value) => {
    setFormData(prev => ({
      ...prev,
      dosages: prev.dosages.map((d, i) => i === index ? {...d, [field]: value} : d)
    }));
  };

  const removeDosage = (index) => {
    setFormData(prev => ({
      ...prev,
      dosages: prev.dosages.filter((_, i) => i !== index)
    }));
  };

  const toggleDrugSelection = (drugId) => {
    setClassFormData(prev => ({
      ...prev,
      selectedDrugs: prev.selectedDrugs.includes(drugId)
        ? prev.selectedDrugs.filter(id => id !== drugId)
        : [...prev.selectedDrugs, drugId]
    }));
  };

  if (loading) {
    return (
      <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100 flex items-center justify-center">
        <div className="text-gray-600">Loading...</div>
      </div>
    );
  }

  if (!currentUser) {
    return (
      <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100 flex items-center justify-center p-6">
        <div className="bg-white rounded-lg shadow-lg p-8 max-w-md w-full">
          <h1 className="text-3xl font-bold text-gray-800 mb-2">MagoMago Pharma Directory</h1>
          <p className="text-gray-600 mb-6">Welcome! Please select an option</p>
          
          {!loginMode && (
            <div className="space-y-3">
              <button
                onClick={() => setLoginMode('register')}
                className="w-full bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 font-medium"
              >
                Register (First Time)
              </button>
              <button
                onClick={() => setLoginMode('login')}
                className="w-full bg-gray-600 text-white px-6 py-3 rounded-lg hover:bg-gray-700 font-medium"
              >
                Login (Returning User)
              </button>
            </div>
          )}

          {loginMode === 'register' && (
            <div className="space-y-4">
              <button onClick={() => setLoginMode(null)} className="text-sm text-blue-600 hover:underline mb-2">← Back</button>
              <input
                type="text"
                value={registrationData.nickname}
                onChange={(e) => setRegistrationData({...registrationData, nickname: e.target.value})}
                className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                placeholder="Nickname *"
              />
              <input
                type="email"
                value={registrationData.email}
                onChange={(e) => setRegistrationData({...registrationData, email: e.target.value})}
                className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                placeholder="Email Address *"
              />
              <select
                value={registrationData.medSchoolYear}
                onChange={(e) => setRegistrationData({...registrationData, medSchoolYear: e.target.value})}
                className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
              >
                <option value="">Select Medical School Year *</option>
                <option value="MS1">MS1</option>
                <option value="MS2">MS2</option>
                <option value="MS3">MS3</option>
                <option value="MS4">MS4</option>
                <option value="Resident">Resident</option>
                <option value="Fellow">Fellow</option>
                <option value="Attending">Attending</option>
                <option value="Faculty">Faculty</option>
              </select>
              <div>
                <input
                  type="text"
                  maxLength="6"
                  value={registrationData.code}
                  onChange={(e) => setRegistrationData({...registrationData, code: e.target.value.replace(/\D/g, '')})}
                  className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                  placeholder="Create 6-Digit Login Code *"
                />
                <p className="text-xs text-gray-500 mt-1">This code will be used to log in along with your email</p>
              </div>
              <button
                onClick={handleRegister}
                className="w-full bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 font-medium"
              >
                Register
              </button>
            </div>
          )}

          {loginMode === 'login' && (
            <div className="space-y-4">
              <button onClick={() => setLoginMode(null)} className="text-sm text-blue-600 hover:underline mb-2">← Back</button>
              <input
                type="email"
                value={loginData.email}
                onChange={(e) => setLoginData({...loginData, email: e.target.value})}
                className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                placeholder="Email Address"
              />
              <input
                type="text"
                maxLength="6"
                value={loginData.code}
                onChange={(e) => setLoginData({...loginData, code: e.target.value.replace(/\D/g, '')})}
                className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                placeholder="6-Digit Code"
              />
              <button
                onClick={handleLogin}
                className="w-full bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700 font-medium"
              >
                Login
              </button>
              <button
                onClick={handleForgotCode}
                className="w-full text-sm text-blue-600 hover:underline flex items-center justify-center gap-2"
              >
                <Mail size={16} />
                Forgot your code?
              </button>
            </div>
          )}
        </div>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-gradient-to-br from-blue-50 to-indigo-100 p-6">
      <div className="max-w-7xl mx-auto">
        <div className="bg-white rounded-lg shadow-lg p-6 mb-6">
          <div className="flex justify-between items-start">
            <div className="flex-1">
              <h1 className="text-3xl font-bold text-gray-800 mb-2">Suvi's Pharmaceutical Directory</h1>
              <p className="text-gray-600">Collaborative drug reference with approval system</p>
            </div>
            <div className="flex gap-2">
              <button
                onClick={() => setShowUsersList(!showUsersList)}
                className="flex items-center gap-2 px-4 py-2 bg-gray-100 rounded-lg hover:bg-gray-200"
              >
                <Users size={20} />
                <span className="font-medium">{users.length} Users</span>
              </button>
              {isAdmin() && (
                <button
                  onClick={() => setShowAdminPanel(!showAdminPanel)}
                  className="flex items-center gap-2 px-4 py-2 bg-purple-100 text-purple-800 rounded-lg hover:bg-purple-200"
                >
                  <Shield size={20} />
                  <span className="font-medium">Admin</span>
                </button>
              )}
            </div>
          </div>
          
          <div className="mt-4 flex items-center justify-between">
            <div>
              <p className="text-sm text-gray-600">
                <span className="font-semibold">{currentUser.nickname}</span> ({currentUser.medSchoolYear})
                {isAdmin() && <span className="ml-2 text-xs bg-purple-100 text-purple-800 px-2 py-1 rounded">Admin</span>}
              </p>
            </div>
            <button onClick={handleLogout} className="text-sm text-blue-600 hover:text-blue-800">
              Logout
            </button>
          </div>

          {showUsersList && (
            <div className="mt-4 p-4 bg-gray-50 rounded-lg">
              <h3 className="font-semibold mb-2">Platform Users</h3>
              <div className="space-y-2 max-h-48 overflow-y-auto">
                {users.map((user, i) => (
                  <div key={i} className="text-sm">
                    <span className="font-medium">{user.nickname}</span> ({user.medSchoolYear})
                    {isAdmin() && <span className="text-gray-500 ml-2">- {user.email}</span>}
                  </div>
                ))}
              </div>
            </div>
          )}

          {showAdminPanel && isAdmin() && (
            <div className="mt-4 p-4 bg-purple-50 rounded-lg border border-purple-200">
              <h3 className="font-semibold mb-3 flex items-center gap-2">
                <History size={20} />
                Edit History
              </h3>
              <div className="space-y-2 max-h-96 overflow-y-auto">
                {editHistory.length === 0 ? (
                  <p className="text-sm text-gray-500">No edit history yet</p>
                ) : (
                  editHistory.map(entry => (
                    <div key={entry.id} className="text-xs bg-white p-3 rounded border">
                      <div className="flex justify-between items-start mb-1">
                        <span className="font-semibold">{entry.action.toUpperCase()}: {entry.itemType}</span>
                        <span className="text-gray-500">{new Date(entry.timestamp).toLocaleString()}</span>
                      </div>
                      <p className="text-gray-700">Item: <span className="font-medium">{entry.itemName}</span></p>
                      <p className="text-gray-600">{entry.details}</p>
                      <p className="text-gray-500 mt-1">By: {entry.userNickname} ({entry.userEmail})</p>
                    </div>
                  ))
                )}
              </div>
            </div>
          )}
        </div>

        <div className="bg-white rounded-lg shadow-lg p-6 mb-6">
          <div className="flex gap-2 mb-4 border-b">
            <button
              onClick={() => setActiveTab('drugs')}
              className={`px-4 py-2 font-medium ${activeTab === 'drugs' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-gray-600 hover:text-gray-800'}`}
            >
              Drugs ({drugs.length})
            </button>
            <button
              onClick={() => setActiveTab('classes')}
              className={`px-4 py-2 font-medium ${activeTab === 'classes' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-gray-600 hover:text-gray-800'}`}
            >
              Drug Classes ({drugClasses.length})
            </button>
            <button
              onClick={() => setActiveTab('pending')}
              className={`px-4 py-2 font-medium ${activeTab === 'pending' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-gray-600 hover:text-gray-800'}`}
            >
              Pending Approval ({pendingDrugs.length})
            </button>
          </div>

          {activeTab !== 'pending' && (
            <>
              <div className="flex gap-4 mb-4">
                <div className="flex-1 relative">
                  <Search className="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-400" size={20} />
                  <input
                    type="text"
                    placeholder={activeTab === 'classes' ? "Search drug classes..." : "Search drugs..."}
                    value={searchTerm}
                    onChange={(e) => setSearchTerm(e.target.value)}
                    className="w-full pl-10 pr-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                  />
                </div>
                <button
                  onClick={() => {
                    setShowKeywordFilter(!showKeywordFilter);
                    if (showKeywordFilter) setKeywordFilter('');
                  }}
                  className={`px-4 py-2 rounded-lg flex items-center gap-2 ${showKeywordFilter ? 'bg-blue-600 text-white' : 'bg-gray-100 hover:bg-gray-200'}`}
                >
                  <Filter size={20} />
                  Keywords
                </button>
                {activeTab === 'drugs' && (
                  <button
                    onClick={() => {
                      setFormData({...formData, submittedBy: currentUser.nickname});
                      setShowAddForm(!showAddForm);
                    }}
                    className="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 flex items-center gap-2"
                  >
                    <Plus size={20} />Add Drug
                  </button>
                )}
                {activeTab === 'classes' && (
                  <button
                    onClick={() => {
                      setClassFormData({...classFormData, submittedBy: currentUser.nickname});
                      setShowClassForm(!showClassForm);
                    }}
                    className="bg-purple-600 text-white px-6 py-2 rounded-lg hover:bg-purple-700 flex items-center gap-2"
                  >
                    <BookOpen size={20} />Add Class
                  </button>
                )}
              </div>

              {showKeywordFilter && (
                <div className="mb-4 p-4 bg-blue-50 rounded-lg">
                  <label className="block text-sm font-medium mb-2">Enter keywords (comma-separated):</label>
                  <input
                    type="text"
                    value={keywordFilter}
                    onChange={(e) => setKeywordFilter(e.target.value)}
                    placeholder="e.g., hypertension, oral, ACE"
                    className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                  />
                  <p className="text-xs text-gray-600 mt-2">Results will be sorted by number of matching keywords</p>
                </div>
              )}
            </>
          )}

          {showAddForm && activeTab === 'drugs' && (
            <div className="border-t pt-4 mt-4">
              <h3 className="text-lg font-semibold mb-4">{editingDrug ? (isAdmin() ? 'Edit Drug (Admin - Direct Edit)' : 'Edit Drug (Requires Reapproval)') : 'Submit New Drug'}</h3>
              <div className="space-y-3">
                <input type="text" value={formData.submittedBy} onChange={(e) => setFormData({...formData, submittedBy: e.target.value})} placeholder="Your nickname *" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <input type="text" value={formData.name} onChange={(e) => setFormData({...formData, name: e.target.value})} placeholder="Drug name *" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <input type="text" value={formData.drugClass} onChange={(e) => setFormData({...formData, drugClass: e.target.value})} placeholder="Drug class" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <input type="text" value={formData.indications} onChange={(e) => setFormData({...formData, indications: e.target.value})} placeholder="Indications (comma-separated)" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <textarea value={formData.contraindications} onChange={(e) => setFormData({...formData, contraindications: e.target.value})} placeholder="Contraindications" rows="2" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <textarea value={formData.adverseEffects} onChange={(e) => setFormData({...formData, adverseEffects: e.target.value})} placeholder="Adverse Effects" rows="2" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <textarea value={formData.boxWarning} onChange={(e) => setFormData({...formData, boxWarning: e.target.value})} placeholder="Box Warning (if applicable)" rows="2" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                
                <div>
                  <label className="block text-sm font-medium mb-2">Routes of Administration</label>
                  <div className="grid grid-cols-3 gap-2">
                    {routeOptions.map(route => (
                      <label key={route} className="flex items-center gap-2 p-2 border rounded cursor-pointer hover:bg-gray-50">
                        <input
                          type="checkbox"
                          checked={formData.routes.includes(route)}
                          onChange={() => toggleRoute(route)}
                          className="rounded"
                        />
                        <span className="text-sm">{route}</span>
                      </label>
                    ))}
                  </div>
                </div>

                <div>
                  <label className="block text-sm font-medium mb-2">Dosages</label>
                  {formData.dosages.map((dosage, idx) => (
                    <div key={idx} className="flex gap-2 mb-2">
                      <input
                        type="text"
                        value={dosage.indication}
                        onChange={(e) => updateDosage(idx, 'indication', e.target.value)}
                        placeholder="For indication"
                        className="flex-1 px-3 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                      />
                      <input
                        type="text"
                        value={dosage.amount}
                        onChange={(e) => updateDosage(idx, 'amount', e.target.value)}
                        placeholder="Amount"
                        className="w-24 px-3 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                      />
                      <input
                        type="text"
                        value={dosage.unit}
                        onChange={(e) => updateDosage(idx, 'unit', e.target.value)}
                        placeholder="Unit (mg, mL)"
                        className="w-32 px-3 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500"
                      />
                      {formData.dosages.length > 1 && (
                        <button onClick={() => removeDosage(idx)} className="text-red-600 hover:text-red-800 p-2">
                          <X size={20} />
                        </button>
                      )}
                    </div>
                  ))}
                  <button onClick={addDosage} className="text-sm text-blue-600 hover:underline">+ Add another dosage</button>
                </div>

                <textarea value={formData.notes} onChange={(e) => setFormData({...formData, notes: e.target.value})} placeholder="Additional notes" rows="3" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <div className="flex gap-2">
                  {editingDrug && isAdmin() ? (
                    <button onClick={() => handleAdminEdit(editingDrug)} className="bg-purple-600 text-white px-6 py-2 rounded-lg hover:bg-purple-700 flex items-center gap-2"><Save size={20} />Save (Admin Direct Edit)</button>
                  ) : (
                    <button onClick={editingDrug ? handleUpdateDrug : handleAddDrug} className="bg-green-600 text-white px-6 py-2 rounded-lg hover:bg-green-700 flex items-center gap-2"><Save size={20} />{editingDrug ? 'Submit Changes' : 'Submit for Approval'}</button>
                  )}
                  <button onClick={resetForm} className="bg-gray-400 text-white px-6 py-2 rounded-lg hover:bg-gray-500 flex items-center gap-2"><X size={20} />Cancel</button>
                </div>
              </div>
            </div>
          )}

          {showClassForm && activeTab === 'classes' && (
            <div className="border-t pt-4 mt-4">
              <h3 className="text-lg font-semibold mb-4">{editingClass ? 'Edit Drug Class' : 'Add New Drug Class'}</h3>
              <div className="space-y-3">
                <input type="text" value={classFormData.submittedBy} onChange={(e) => setClassFormData({...classFormData, submittedBy: e.target.value})} placeholder="Your nickname *" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <input type="text" value={classFormData.name} onChange={(e) => setClassFormData({...classFormData, name: e.target.value})} placeholder="Class name *" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <input type="text" value={classFormData.conditionClass} onChange={(e) => setClassFormData({...classFormData, conditionClass: e.target.value})} placeholder="Condition class (e.g., Cardiovascular, Respiratory)" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                
                <div>
                  <label className="block text-sm font-medium mb-2">Select Drugs for this Class</label>
                  <div className="max-h-48 overflow-y-auto border rounded-lg p-3 space-y-2">
                    {drugs.map(drug => (
                      <label key={drug.id} className="flex items-center gap-2 p-2 hover:bg-gray-50 rounded cursor-pointer">
                        <input
                          type="checkbox"
                          checked={classFormData.selectedDrugs.includes(drug.id)}
                          onChange={() => toggleDrugSelection(drug.id)}
                          className="rounded"
                        />
                        <span className="text-sm">{drug.name}</span>
                      </label>
                    ))}
                  </div>
                  <p className="text-xs text-gray-500 mt-1">{classFormData.selectedDrugs.length} drug(s) selected</p>
                </div>

                <textarea value={classFormData.description} onChange={(e) => setClassFormData({...classFormData, description: e.target.value})} placeholder="Description" rows="2" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <textarea value={classFormData.mechanism} onChange={(e) => setClassFormData({...classFormData, mechanism: e.target.value})} placeholder="Mechanism of action" rows="2" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <input type="text" value={classFormData.commonSideEffects} onChange={(e) => setClassFormData({...classFormData, commonSideEffects: e.target.value})} placeholder="Common side effects" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <textarea value={classFormData.notes} onChange={(e) => setClassFormData({...classFormData, notes: e.target.value})} placeholder="Additional notes" rows="2" className="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-blue-500" />
                <div className="flex gap-2">
                  <button onClick={editingClass ? handleUpdateClass : handleAddClass} className="bg-green-600 text-white px-6 py-2 rounded-lg hover:bg-green-700 flex items-center gap-2"><Save size={20} />{editingClass ? 'Update' : 'Save'}</button>
                  <button onClick={resetClassForm} className="bg-gray-400 text-white px-6 py-2 rounded-lg hover:bg-gray-500 flex items-center gap-2"><X size={20} />Cancel</button>
                </div>
              </div>
            </div>
          )}
        </div>

        {activeTab === 'drugs' && (
          filteredDrugs.length === 0 ? (
            <div className="bg-white rounded-lg shadow-lg p-12 text-center">
              <p className="text-gray-500 text-lg">{searchTerm || keywordFilter ? 'No drugs found.' : 'No approved drugs yet.'}</p>
            </div>
          ) : (
            <div className="grid gap-4">
              {filteredDrugs.map(drug => (
                <div key={drug.id} className="bg-white rounded-lg shadow-lg p-6">
                  <div className="flex justify-between items-start mb-4">
                    <div className="flex-1">
                      <div className="flex items-center gap-3 mb-2">
                        <h3 className="text-2xl font-bold text-gray-800">{drug.name}</h3>
                        {drug.drugClass && <span className="bg-purple-100 text-purple-800 px-3 py-1 rounded-full text-sm font-medium">{drug.drugClass}</span>}
                        {drug.matchCount && <span className="bg-green-100 text-green-800 px-2 py-1 rounded-full text-xs font-medium">{drug.matchCount} keyword matches</span>}
                      </div>
                      <div className="flex flex-wrap gap-2">
                        {drug.indications.map((ind, i) => <span key={i} className="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-sm">{ind}</span>)}
                      </div>
                    </div>
                    <div className="flex gap-2">
                      <button onClick={() => startEdit(drug)} className="text-blue-600 hover:text-blue-800 p-2"><Edit2 size={20} /></button>
                      <button onClick={() => handleDeleteDrug(drug.id)} className="text-red-600 hover:text-red-800 p-2"><Trash2 size={20} /></button>
                    </div>
                  </div>
                  
                  {drug.routes && drug.routes.length > 0 && (
                    <div className="mb-3">
                      <span className="font-semibold">Routes: </span>
                      <span className="text-gray-600">{drug.routes.join(', ')}</span>
                    </div>
                  )}
                  
                  {drug.dosages && drug.dosages.length > 0 && drug.dosages[0].amount && (
                    <div className="mb-3">
                      <span className="font-semibold">Dosages: </span>
                      <div className="text-gray-600 ml-4">
                        {drug.dosages.map((d, i) => d.amount && (
                          <div key={i}>• {d.indication ? `${d.indication}: ` : ''}{d.amount} {d.unit}</div>
                        ))}
                      </div>
                    </div>
                  )}
                  
                  {drug.contraindications && (
                    <div className="mb-3">
                      <span className="font-semibold">Contraindications: </span>
                      <span className="text-gray-600">{drug.contraindications}</span>
                    </div>
                  )}
                  
                  {drug.adverseEffects && (
                    <div className="mb-3">
                      <span className="font-semibold">Adverse Effects: </span>
                      <span className="text-gray-600">{drug.adverseEffects}</span>
                    </div>
                  )}
                  
                  {drug.boxWarning && (
                    <div className="mb-3 p-3 bg-red-50 border border-red-200 rounded">
                      <span className="font-semibold text-red-800">⚠️ Box Warning: </span>
                      <span className="text-red-700">{drug.boxWarning}</span>
                    </div>
                  )}
                  
                  {drug.notes && (
                    <div className="mb-3">
                      <span className="font-semibold">Notes: </span>
                      <span className="text-gray-600">{drug.notes}</span>
                    </div>
                  )}

                  <div className="text-xs text-gray-500 mt-4 pt-3 border-t">
                    Submitted by {drug.submitterNickname || drug.submittedBy} • Approved {new Date(drug.dateApproved).toLocaleDateString()}
                    {isAdmin() && drug.submitterEmail && <span className="ml-2">({drug.submitterEmail})</span>}
                  </div>
                </div>
              ))}
            </div>
          )
        )}

        {activeTab === 'classes' && (
          filteredClasses.length === 0 ? (
            <div className="bg-white rounded-lg shadow-lg p-12 text-center">
              <p className="text-gray-500 text-lg">{searchTerm ? 'No classes found.' : 'No drug classes yet.'}</p>
            </div>
          ) : (
            <div className="grid gap-4">
              {filteredClasses.map(cls => {
                const classDrugs = cls.selectedDrugs ? drugs.filter(d => cls.selectedDrugs.includes(d.id)) : getDrugsByClass(cls.name);
                return (
                  <div key={cls.id} className="bg-white rounded-lg shadow-lg p-6">
                    <div className="flex justify-between items-start mb-4">
                      <div className="flex-1">
                        <h3 className="text-2xl font-bold text-purple-800">{cls.name}</h3>
                        {cls.conditionClass && <span className="text-sm text-gray-600">Condition: {cls.conditionClass}</span>}
                        <p className="text-sm text-gray-500 mt-1">{classDrugs.length} drug(s)</p>
                      </div>
                      <div className="flex gap-2">
                        <button onClick={() => startEditClass(cls)} className="text-blue-600 hover:text-blue-800 p-2"><Edit2 size={20} /></button>
                        <button onClick={() => handleDeleteClass(cls.id)} className="text-red-600 hover:text-red-800 p-2"><Trash2 size={20} /></button>
                      </div>
                    </div>
                    {cls.description && <div className="mb-3"><span className="font-semibold">Description: </span><span className="text-gray-600">{cls.description}</span></div>}
                    {cls.mechanism && <div className="mb-3"><span className="font-semibold">Mechanism: </span><span className="text-gray-600">{cls.mechanism}</span></div>}
                    {cls.commonSideEffects && <div className="mb-3"><span className="font-semibold">Common Side Effects: </span><span className="text-gray-600">{cls.commonSideEffects}</span></div>}
                    {cls.notes && <div className="mb-3"><span className="font-semibold">Notes: </span><span className="text-gray-600">{cls.notes}</span></div>}
                    {classDrugs.length > 0 && (
                      <div className="mt-4 pt-3 border-t">
                        <p className="text-sm font-semibold text-gray-700 mb-2">Drugs in this class:</p>
                        <div className="flex flex-wrap gap-2">
                          {classDrugs.map(d => <span key={d.id} className="bg-gray-100 text-gray-700 px-2 py-1 rounded text-sm">{d.name}</span>)}
                        </div>
                      </div>
                    )}
                  </div>
                );
              })}
            </div>
          )
        )}

        {activeTab === 'pending' && (
          pendingDrugs.length === 0 ? (
            <div className="bg-white rounded-lg shadow-lg p-12 text-center">
              <p className="text-gray-500 text-lg">No drugs pending approval.</p>
            </div>
          ) : (
            <div className="grid gap-4">
              {pendingDrugs.map(drug => (
                <div key={drug.id} className="bg-white rounded-lg shadow-lg p-6 border-2 border-yellow-200">
                  <div className="flex items-start justify-between mb-4">
                    <div className="flex-1">
                      <div className="flex items-center gap-3 mb-2">
                        <h3 className="text-2xl font-bold text-gray-800">{drug.name}</h3>
                        {drug.drugClass && <span className="bg-purple-100 text-purple-800 px-3 py-1 rounded-full text-sm font-medium">{drug.drugClass}</span>}
                        <span className="bg-yellow-100 text-yellow-800 px-3 py-1 rounded-full text-sm font-medium flex items-center gap-1">
                          <AlertCircle size={16} />Pending ({drug.confirmations.length}/2)
                        </span>
                      </div>
                      <div className="flex flex-wrap gap-2">
                        {drug.indications.map((ind, i) => <span key={i} className="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-sm">{ind}</span>)}
                      </div>
                    </div>
                    <button onClick={() => handleDeletePending(drug.id)} className="text-red-600 hover:text-red-800 p-2"><Trash2 size={20} /></button>
                  </div>
                  
                  {drug.routes && drug.routes.length > 0 && <div className="mb-3"><span className="font-semibold">Routes: </span><span className="text-gray-600">{drug.routes.join(', ')}</span></div>}
                  {drug.dosages && drug.dosages.length > 0 && drug.dosages[0].amount && (
                    <div className="mb-3">
                      <span className="font-semibold">Dosages: </span>
                      <div className="text-gray-600 ml-4">
                        {drug.dosages.map((d, i) => d.amount && <div key={i}>• {d.indication ? `${d.indication}: ` : ''}{d.amount} {d.unit}</div>)}
                      </div>
                    </div>
                  )}
                  {drug.contraindications && <div className="mb-3"><span className="font-semibold">Contraindications: </span><span className="text-gray-600">{drug.contraindications}</span></div>}
                  {drug.adverseEffects && <div className="mb-3"><span className="font-semibold">Adverse Effects: </span><span className="text-gray-600">{drug.adverseEffects}</span></div>}
                  {drug.boxWarning && (
                    <div className="mb-3 p-3 bg-red-50 border border-red-200 rounded">
                      <span className="font-semibold text-red-800">⚠️ Box Warning: </span>
                      <span className="text-red-700">{drug.boxWarning}</span>
                    </div>
                  )}
                  {drug.notes && <div className="mb-3"><span className="font-semibold">Notes: </span><span className="text-gray-600">{drug.notes}</span></div>}
                  
                  <div className="mt-4 pt-4 border-t">
                    <p className="text-sm text-gray-600 mb-2">
                      Submitted by {drug.submitterNickname || drug.submittedBy}
                      {isAdmin() && drug.submitterEmail && ` (${drug.submitterEmail})`} on {new Date(drug.dateSubmitted).toLocaleDateString()}
                    </p>
                    
                    {drug.confirmations.length > 0 && (
                      <div className="mb-3">
                        <p className="text-sm font-semibold text-gray-700 mb-1">Confirmations:</p>
                        {drug.confirmations.map((c, i) => (
                          <p key={i} className="text-xs text-gray-600">
                            ✓ {c.nickname || c.name}
                            {isAdmin() && c.email && ` (${c.email})`} - {new Date(c.date).toLocaleDateString()}
                          </p>
                        ))}
                      </div>
                    )}
                    
                    <div className="flex gap-2 items-center mt-3">
                      <input
                        type="text"
                        value={confirmerName}
                        onChange={(e) => setConfirmerName(e.target.value)}
                        placeholder="Your nickname to confirm"
                        className="flex-1 px-3 py-2 border rounded-lg text-sm focus:ring-2 focus:ring-green-500"
                      />
                      <button
                        onClick={() => handleConfirmDrug(drug.id, confirmerName)}
                        className="bg-green-600 text-white px-4 py-2 rounded-lg hover:bg-green-700 flex items-center gap-2"
                      >
                        <Check size={18} />Confirm
                      </button>
                    </div>
                    <p className="text-xs text-gray-500 mt-2">
                      {currentUser.email.toLowerCase() === 'suvibuii@gmail.com' 
                        ? '✨ As MagoMago, your confirmation instantly approves this drug'
                        : 'Needs 2 confirmations or 1 from MagoMago to be approved'}
                    </p>
                  </div>
                </div>
              ))}
            </div>
          )
        )}
      </div>
    </div>
  );
}